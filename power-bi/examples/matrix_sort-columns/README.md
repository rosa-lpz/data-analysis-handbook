# Matrix Table - Fruit Quality

## Target Layout

```
Quality Index | Apple1 | Apple2    | Apple3     | Apple4 | Apple5 | Apple6     | Apple7 | Percentage | Date Update
Count         | 35     | 23        | 16         | 76     | 7      | 10         | 87     | 1          | 01/01/26
Color         | N/A    | Passed    | Not Passed | Passed | Passed | Passed     | Passed | 0.7        | 01/02/26
Flavor        | Passed | N/A       | Passed     | N/A    | N/A    | Not Passed | Passed | 0.6        | 01/03/26
Freshness     | Passed | Not Passed| Passed     | Passed | Passed | Passed     | Passed | 0.4        | 01/04/26
```

---

## Option 1 — Table Visual (flat table)

**File:** `data/matrix/fruit_quality.csv`

Single flat table — use with a **Table visual**.

| Column | Type | Notes |
|---|---|---|
| `Quality_Index` | Text | Row label |
| `Apple1`–`Apple7` | Text | Mixed values: numbers, Passed, Not Passed, N/A |
| `Percentage` | Decimal | 1, 0.7, 0.6, 0.4 |
| `Date_Update` | Date | One date per row |

> All Apple columns must be **Text** type since they hold mixed values.

---

## Option 2 — Matrix Visual (normalized, 2 tables)

Use a **Matrix visual** with rows = `Quality_Index`, columns = `Apple_Name`, values = `Status`.

### `data/matrix/quality_checks.csv`

Normalized fact table — 28 rows (one per Quality_Index × Apple combination).

| Column | Type | Example |
|---|---|---|
| `Quality_Index` | Text | Color |
| `Apple_Name` | Text | Apple2 |
| `Status` | Text | Passed |

### `data/matrix/quality_metrics.csv`

Dimension/metrics table — 4 rows (one per Quality_Index).

| Column | Type | Example |
|---|---|---|
| `Quality_Index` | Text | Color |
| `Percentage` | Decimal | 0.7 |
| `Date_Update` | Date | 01/02/26 |

### Matrix Visual Config

- **Rows**: `Quality_Index`
- **Columns**: `Apple_Name`
- **Values**: `Status` (aggregated as **First** or **Last** — text field)
- Add `Percentage` and `Date_Update` as extra Values from `quality_metrics`
- Join both tables on `Quality_Index`

---

## Sorting Apple_Name columns by Count (descending rank)

### Step 1 — `Count_Sort` column in `quality_checks.csv`

Each row already carries the apple's count value in `Count_Sort` (same value repeated for every `Quality_Index` of that apple).

| Apple_Name | Count_Sort |
|---|---|
| Apple7 | 87 |
| Apple4 | 76 |
| Apple1 | 35 |
| Apple2 | 23 |
| Apple3 | 16 |
| Apple6 | 10 |
| Apple5 | 7 |

### Step 2 — DAX calculated column `Count_Rank`

Add this calculated column to the `quality_checks` table in Power BI:

```dax
Count_Rank =
RANKX(
    ALL(quality_checks[Count_Sort]),
    quality_checks[Count_Sort],
    ,
    DESC,
    Dense
)
```

**Breakdown:**
- `ALL(quality_checks[Count_Sort])` — ranks over all distinct count values, ignoring row context
- `quality_checks[Count_Sort]` — the value to rank for the current row
- `DESC` — rank 1 = highest count (Apple7 = 87), rank 7 = lowest (Apple5 = 7)
- `Dense` — no gaps in rank numbers if two apples had the same count

**Result:**

| Apple_Name | Count_Sort | Count_Rank |
|---|---|---|
| Apple7 | 87 | 1 |
| Apple4 | 76 | 2 |
| Apple1 | 35 | 3 |
| Apple2 | 23 | 4 |
| Apple3 | 16 | 5 |
| Apple6 | 10 | 6 |
| Apple5 | 7 | 7 |

### Step 3 — Apply sort in Power BI

1. In the **Data view**, select the `Apple_Name` column in `quality_checks`
2. Go to **Column Tools → Sort by Column → Count_Rank**
3. Matrix columns will now display in descending count order: Apple7 → Apple4 → Apple1 → Apple2 → Apple3 → Apple6 → Apple5

---

## Recommendation

| Option | When to use |
|---|---|
| Option 1 (`fruit_quality.csv`) | Simple display, layout matches exactly, no dynamic filtering needed |
| Option 2 (`quality_checks.csv` + `quality_metrics.csv`) | Need to filter/slice by individual apple, or plan to add more apples dynamically |


# how can I remove the totals from the Matrix table visual

In the Matrix visual, go to the Format pane and turn off both row and column totals:

Row totals:

Format pane → Row subtotals
Toggle Row subtotals → Off
Column totals:

Format pane → Column subtotals
Toggle Column subtotals → Off
Alternatively, both are also available under Format pane → Subtotals, where you can control:

Row subtotals — hides the total row at the bottom
Column subtotals — hides the total column on the right
Row subtotal position / Column subtotal position — if you keep them, you can move them to top/left instead

# Rank column in quality_index

## Create the QI_Rank column

### Quality index rank (column)
```bash
QI_Rank =
SWITCH(
    quality_checks[Quality_Index],
    "Count",     1,
    "Color",     2,
    "Flavor",    3,
    "Freshness", 4
)
```
### Quality index rank (measure)
```bash
QI_Rank =
SWITCH(
    SELECTEDVALUE(quality_checks[Quality_Index]),
    "Count",     1,
    "Color",     2,
    "Flavor",    3,
    "Freshness", 4
)
```

Measures can't be used for **Sort by Column** — that requires a calculated column. However, if you still want a measure for use in visuals (e.g., as a value field):



**Key difference vs calculated column:**

| | Calculated Column | Measure |
|---|---|---|
| Evaluated | Row by row at data refresh | On demand in visual context |
| Can use for Sort by Column | Yes | **No** |
| Works in matrix rows/values | Yes | Yes |

For sorting `Quality_Index` rows in the matrix, you still need the calculated column version. The measure is only useful if you want to display the rank number as a value inside the visual itself.


##  Add the  QI_Rank column directly to the CSV

Add the rank directly in quality_checks.csv so no DAX is needed at all:

| Quality_Index | QI_Rank |
|---|---|
| Count | 1 |
| Color | 2 |
| Flavor | 3 |
| Freshness | 4 |

Then in Power BI just set **Sort by Column → `QI_Rank`** — no DAX required.


## Create a  QI_Rank table with dax
```dax
qi_rank =
DATATABLE(
    "Quality_Index", STRING,
    "QI_Rank",       INTEGER,
    {
        { "Count",     1 },
        { "Color",     2 },
        { "Flavor",    3 },
        { "Freshness", 4 }
    }
)
```

Create it via **Modeling → New Table** in Power BI. Then:

1. Create a relationship: `qi_rank[Quality_Index]` → `quality_checks[Quality_Index]`
2. In **Data view**, select `quality_checks[Quality_Index]`
3. **Column Tools → Sort by Column → `QI_Rank`** (from the related `qi_rank` table — note: this only works if the column is brought in directly; if it doesn't appear, use Option 2 below)

> **Note:** Sort by Column requires the sort column to be in the **same table**. If `QI_Rank` from `qi_rank` doesn't appear in the dropdown, add a calculated column in `quality_checks` that pulls the rank via `RELATED`:

```dax
QI_Rank =
RELATED(qi_rank[QI_Rank])
```

Then sort `Quality_Index` by that `QI_Rank` calculated column.

## References

How to re-arrange columns in Power BI Visual
https://community.fabric.microsoft.com/t5/Desktop/How-to-re-arrange-columns-in-Power-BI-Visual/td-p/4145024