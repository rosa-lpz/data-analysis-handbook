
# FILTERS
```bash
CALCULATETABLE(<expression>[, <filter1> [, <filter2> [, …]]])
```
https://learn.microsoft.com/en-us/dax/calculatetable-function-dax


# Examples

# Filter fruits_db by count
## Read-only query
```bash
EVALUATE
 FILTER ( 'fruits_db', [Count] > 20 ) )
ORDER BY [Count] DESC
```


## Simple filter - Count > 20
```bash
fruits_filtered_count =
FILTER(
    'fruits_db',
    'fruits_db'[Count] > 20
)
```


## Top N rows Count > 20 and ordered
```bash
fruits_filtered_top =
TOPN(
    10,
    FILTER(
        'fruits_db',
        'fruits_db'[Count] > 20
    ),
    'fruits_db'[Count],
    DESC
)
```

## Top total rows Count > 20 and ordered
```bash
```bash
fruits_filtered_count = 
TOPN(
    COUNTROWS( 'fruits_db' ),
    FILTER( 'fruits_db', [Count] > 20 ),
    [Count],
    DESC
)
```


# Filter fruits_db by color value 
## Read-only query
```bash
EVALUATE
    FILTER( 'fruits_db', [Color] = "Passed" )
ORDER BY [Fruit] ASC
```
The only correction: DAX string literals use double quotes "Passed", not single quotes. Single quotes are reserved for table names like

## Create calculated table
```bash
fruits_filtered_color = 
TOPN(
    COUNTROWS( 'fruits_db' ),
    FILTER( 'fruits_db', [Color] = "Passed" ),
    [Fruit],
    ASC
)
```


# Measure
```bash
fruits_filtered_count =
CALCULATE(
    COUNTROWS('fruits_db'),
    'fruits_db'[Count] > 20
)
```

# Summary
| Goal           | Correct DAX   |
| -------------- | ------------- |
| Filter rows    | `FILTER()`    |
| Top rows       | `TOPN()`      |
| Count rows     | `COUNTROWS()` |
| Filtered count | `CALCULATE()` |



Your DAX expression has a **logic issue**. In **Microsoft Power BI**, the function **TOPN** expects the **first argument to be a fixed number**, but you used **COUNTROWS**, which returns a dynamic value. Also, `TOPN` is unnecessary if you only want rows where `[Count] > 20`.

