

# DATATABLE function

You can create static tables in DAX using the DATATABLE function. This article describes the syntax of this new feature and shows when and how to use it


If you want to keep the data visible, you might use a calculated table with the union of different rows, such as the following expression:

```bash
Segments_UnionRows =
UNION (
    ROW ( "Price Range", "Low", "Min Price", CURRENCY ( 0 ), "Max Price", CURRENCY ( 10 ) ),
    ROW ( "Price Range", "Medium", "Min Price", 10, "Max Price", 100 ),
    ROW ( "Price Range", "High", "Min Price", 100, "Max Price", 9999999 )
)

```

Such a syntax is verbose, because you replicate the column names in each row, even if only the first one defined the column names in the output table. Moreover, you do not have a direct control over the data type of the columns, which are inferred by the expressions of the values included in the ROW syntax.

A better alternative is the new DATATABLE function, as in the following example:

```bash
Segments_Datatable =
DATATABLE (
    "Price Range", STRING,
    "Min Price", CURRENCY,
    "Max Price", CURRENCY,
    {
        { "Low", 0, 10 },
        { "Medium", 10, 100 },
        { "High", 100, 9999999 }
    }
)

```

## References
* https://www.sqlbi.com/articles/create-static-tables-in-dax-using-the-datatable-function/
* https://learn.microsoft.com/en-us/dax/datatable-function-dax


# Table constructor
Returns a table of one or more columns.
```bash
EVALUATE
    {
        (1.5, DATE(2017, 1, 1), CURRENCY(199.99), "A"),
        (2.5, DATE(2017, 1, 2), CURRENCY(249.99), "B"),
        (3.5, DATE(2017, 1, 3), CURRENCY(299.99), "C")
    }
```

## References
* https://learn.microsoft.com/en-us/dax/table-constructor