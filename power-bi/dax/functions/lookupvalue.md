# LOOKUPVALUE

Applies to:  Calculated column  Calculated table  Measure  Visual calculation

Returns the value for the row that meets all criteria specified by one or more search conditions.

## Syntax
```bash
DAX
LOOKUPVALUE (
    <result_columnName>,
    <search_columnName>,
    <search_value>
    [, <search2_columnName>, <search2_value>]…
    [, <alternateResult>]
)
```
## Parameters
Term	Definition
result_columnName	The name of an existing column that contains the value you want to return. It can't be an expression.
search_columnName	The name of an existing column. It can be in the same table as result_columnName or in a related table. It can't be an expression. You can specify multiple pairs of search_columnName and search_value.
search_value	The value to search for in search_columnName. You can specify multiple pairs of search_columnName and search_value.
alternateResult	(Optional) The value returned when the context for result_columnName is filtered down to zero or more than one distinct value. If not specified, the function returns BLANK when result_columnName is filtered down to zero values, or an error when the context for result_columnName has more than one distinct value.

|Term|	Definition|
|---|---|
|result_columnName|	The name of an existing column that contains the value you want to return. It can't be an expression.
|search_columnName	|The name of an existing column. It can be in the same table as result_columnName or in a related table. It can't be an expression. You can specify multiple pairs of search_columnName and search_value.|
|search_value	|The value to search for in search_columnName. You can specify multiple pairs of search_columnName and search_value.|
|alternateResult	(Optional) |The value returned when the context for result_columnName is filtered down to zero or more than one distinct value. If not specified, the function returns BLANK when result_columnName is filtered down to zero values, or an error when the context for result_columnName has more than one distinct value.|


## Return value
The value of result_columnName at the row where all pairs of search_columnName and search_value have an exact match.

If no match satisfies all the search values, the function returns BLANK or alternateResult (if specified). In other words, the function doesn't return a lookup value if only some of the criteria match.

If multiple rows match the search values and the values in the result_columnName for these rows are identical, that value is returned. However, if result_columnName returns different values, the function returns an error or alternateResult (if specified).

# References
* https://learn.microsoft.com/en-us/dax/lookupvalue-function-dax