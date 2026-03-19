# DAX Functions
## Content
* [Logical Functions](#logical-functions)
    * [IF](#if)
* [Text functions](#text-functions)
* [Date and time functions](#date-and-time-functions)
    
## Logical Functions

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