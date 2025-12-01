We change column names **and** perform a **union** (Append) of two tables in Power Query.
 In fact, this is the **recommended** and **most efficient** way to union tables in Power BI.

------

# **How to Change Column Names + Append (Union) in Power Query**

## **Step 1: Change Column Names**

You need matching column names before appending.

### **Method A — Rename manually**

1. Open **Power Query Editor**
2. Right-click column header → **Rename**
3. Type new name → Enter

### **Method B — Rename using M code**

If you want multiple renames at once, use:

```powerquery
RenamedColumns = Table.RenameColumns(
    Source,
    {
        {"OldName1", "NewName1"},
        {"OldName2", "NewName2"}
    }
)
```

Just replace names as needed.

------

## **Step 2: Append (Union) the Two Tables**

Once the column names match:

1. **Home → Append Queries**
2. Select **Two tables**
3. Pick Table A and Table B
4. Click **OK**

Power Query will stack the rows (UNION).

------

# Important Notes

### ✔ Power Query matches columns *by name*, not position

If column names differ, the append will create separate columns and produce nulls.
 **Therefore, always rename to matching names first.**

### ✔ You can perform both steps in a single query

Rename → Append.

### ✔ Power Query is more efficient than DAX UNION

It folds work to the data source and reduces model size.

------

# Example: Rename Columns + Append in M

```powerquery
TableA_Renamed = Table.RenameColumns(
    TableA,
    {
        {"CustID", "CustomerID"},
        {"Amt", "Amount"}
    }
),

TableB_Renamed = Table.RenameColumns(
    TableB,
    {
        {"Customer_Id", "CustomerID"},
        {"Value", "Amount"}
    }
),

FinalUnion = Table.Combine({TableA_Renamed, TableB_Renamed})
```

`Table.Combine` is Power Query’s native union.

------

# Summary

Yes — you can (and should):

### **1. Rename columns in Power Query**

### **2. Append queries (union of tables)**

This is the most efficient way to combine tables in Power BI.

------

If you'd like, tell me your two table names + column names, and I’ll generate the exact Power Query steps for your scenario.