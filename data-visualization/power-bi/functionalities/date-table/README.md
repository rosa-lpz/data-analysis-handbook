# Calendar (date table) that works across all Power BI pages

To make a **calendar (date table) that works across all Power BI pages**, the **best and recommended approach** is to create **one central Date/Calendar table** in your data model and use it everywhere.



## Characteristics

- One calendar = consistent filtering across all pages
- Works with slicers, visuals, time intelligence (YTD, MTD, YoY)
- Faster and easier to maintain
- Required for many DAX time functions



## Create the Calendar Table (DAX)

Go to **Modeling → New table** and paste:

```DAX
Calendar =
VAR MinDate =
    DATE(2018, 1, 1)
VAR MaxDate =
    DATE(2030, 12, 31)
RETURN
ADDCOLUMNS (
    CALENDAR ( MinDate, MaxDate ),
    "Year", YEAR ( [Date] ),
    "Month Number", MONTH ( [Date] ),
    "Month Name", FORMAT ( [Date], "MMMM" ),
    "Year-Month", FORMAT ( [Date], "YYYY-MM" ),
    "Quarter", "Q" & FORMAT ( [Date], "Q" ),
    "Week Number", WEEKNUM ( [Date], 2 ),
    "Day", DAY ( [Date] ),
    "Day Name", FORMAT ( [Date], "dddd" ),
    "Is Weekend", IF ( WEEKDAY ( [Date], 2 ) > 5, TRUE, FALSE )
)
```

Note: Adjust min/max dates to the data range.



## Date Table should be marked as date table (IMPORTANT)

1. Select the **Calendar** table
2. Go to **Table tools → Mark as date table**
3. Choose the **Date** column

This enables proper time intelligence across pages.

------



## Create Relationships

For **every fact table**:

- Link `Calendar[Date]` → `FactTable[DateColumn]`
- Relationship:
  - **Many-to-one**
  - **Single direction**
  - Calendar filters facts

Note: We shouldn't create multiple calendar tables.



## Use the Calendar in Slicers (All Pages)

### Option A: Page-Level Consistency (Best UX)

1. Add a **Date slicer** using `Calendar[Date]`
2. Go to **View → Sync slicers**
3. Sync the slicer across **all pages**
4. Choose:
   - **Sync** ✔
   - **Visible** (optional per page)

Now one calendar controls the entire report.

------

## Create Multiple Slicer Types (Optional)

From the same Calendar table:

- Year slicer → `Calendar[Year]`
- Month slicer → `Calendar[Month Name]`
- Relative date slicer → `Calendar[Date]`

All will work together automatically.

------



## Pro Tips 

### Sort Month Correctly

- Select **Month Name**
- Sort by **Month Number**

### Fiscal Calendar (if needed)

```DAX
Fiscal Year =
IF ( MONTH ( [Date] ) >= 7, YEAR ( [Date] ) + 1, YEAR ( [Date] ) )
```

### Disable Auto Date/Time

Go to:

```
File → Options → Data Load → Time Intelligence
☐ Auto date/time
```

This avoids hidden calendars that break consistency.

Reference: https://learn.microsoft.com/en-us/power-bi/transform-model/desktop-auto-date-time

------



## NOT to Do

- One calendar per page
- Using auto date hierarchy
- Multiple relationships between fact tables and different date tables
- Using fact table dates directly in slicers



## Final Result

We get:

- One calendar controlling **all Power BI pages**
- Accurate time intelligence
- Cleaner model
- Easier maintenance

