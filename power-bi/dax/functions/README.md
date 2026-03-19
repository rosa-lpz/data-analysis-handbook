# DAX Functions
## Content
* [Simple Aggregations](#simple-aggregations)
* [Logical Functions](#logical-functions)
    * [IF](#if)
* [Text functions](#text-functions)
* [Date and time functions](#date-and-time-functions)
    
## Simple Aggregations
* SUM(<column>) adds all the numbers in a column
* AVERAGE(<column>) returns the average (arithmetic mean) of all numbers in a column
* MEDIAN(<column>) returns the median of numbers in a column
* MIN/MAX(<column>) returns the smallest/biggest value in a column
* COUNT(<column>) counts the number of cells in a column that contain non-blank values
* DISTINCTCOUNT(<column>) counts the number of distinct values in a column.

## Logical Functions
* IF(<logical_test>, <value_if_true>[, <value_if_false>]) Checks a condition, and returns a certain value depending on whether it is true or false.
* AND(<logical 1>, <logical 2>) Checks whether both arguments are TRUE, and returns TRUE if both arguments are TRUE. Otherwise, it returns FALSE.
* OR(<logical 1>, <logical 2>) Checks whether one of the arguments is TRUE to return TRUE. The function returns FALSE if both arguments are FALSE.
* NOT(<logical>) Changes TRUE to FALSE and vice versa.
* SWITCH(<expression>, <value>, <result>[, <value>, <result>]…[, <else>]) Evaluates an expression against a list of values and returns one of possible results
* IFERROR(<value>, <value_if_error>) Returns value_if_error if the first expression is an error and the value of the expression itself otherwise.

### IF
Check the result of an expression and create conditional results

**Syntax**
```bash
IF(Condition, TrueResult, FalseResult)
```

#### Example
Create a new column wih IF function. We can follow this syntax:
```bash
NewColumn = IF(condition, value_if_true, value_if_false)
```
SalesCategory column:
```bash
SalesCategory = IF(Sales[Amount] > 1000, "High", "Low")
```

## Text functions

### LEFT
Returns the specified number of characters from the start of a text
```bash
LEFT(<text>, <num_chars>) 
```
 c

### LOWER
Converts a text string to all lowercase letters
```bash
LOWER(<text>)
```
### UPPER
Converts a text string to all uppercase letters
```bash
UPPER (<text>) 
```
### REPLACE
Replaces part of a text string with a different text string.
```bash
REPLACE(<old_text>, <start_num>, <num_chars>, <new_text>) 
```


## Date and time functions

### CALENDAR 
Generates a column of continuous sets of dates
```bash
CALENDAR(<start date>, <end date>)
```
### DATE
Returns the specified date in the datetime format
```bash
DATE(<year>, <month>, <day>) 
```

### WEEKDAY 
Returns 1-7 corresponding to the day of the week of a date (return_type indicates week start and end (1: Sunday-Saturday, 2: Monday Sunday)
```bash
WEEKDAY(<date>, <return_type>) 
```


# REFERENCES
* DataQuest
    * [PDF](cheatsheets/dataquest_power-bi_cheat-sheet.pdf) |[Website](https://www.dataquest.io/cheat-sheet/power-bi-cheat-sheet/) | DataQuest - Power BI Cheat Sheet
* DataCamp
    * [PDF](cheatsheets/datacamp_power-bi_cheat-sheet.pdf) | [Website](https://www.datacamp.com/cheat-sheet/power-bi-cheat-sheet) | Power BI 
    * [PDF](cheatsheets/datacamp_power-bi_tables-in-power-query-m.pdf) | [Website](https://www.datacamp.com/cheat-sheet/working-with-tables-in-power-query-m-in-power-bi) | Working with Tables in Power Query M  
    * [PDF](cheatsheets/datacamp_power-bi_data-transformation_power-query-m.pdf) | [Website](https://www.datacamp.com/cheat-sheet/data-transformation-with-power-query-m-in-power-bi) | Data Transformation with Power Query M  
    * [PDF](cheatsheets/datacamp_power-bi-formulas-in-DAX_cheat-sheet.pdf) | [Website](https://www.datacamp.com/cheat-sheet/dax-cheat-sheet) | Formulas-in-DAX