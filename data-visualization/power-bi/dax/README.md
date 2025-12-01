# DAX overview

​			  			 	   	

Data Analysis Expressions (DAX) is a  formula expression language used in Analysis Services, Power BI, and  Power Pivot in Excel. DAX formulas include functions, operators, and  values to perform advanced calculations and queries on data in related  tables and columns in tabular data models.

This article provides only a basic introduction to the most important concepts in DAX. It describes DAX as it applies to all the products  that use it. Some functionality may not apply to certain products or use cases. Refer to your product's documentation describing its particular  implementation of DAX.

## Calculations

DAX formulas are used in measures, calculated columns, calculated tables, and row-level security.



## Queries

DAX queries can be created and run in SQL Server Management Studio  (SSMS) and open-source tools like DAX Studio (daxstudio.org). Unlike DAX calculation formulas, which can only be created in tabular data models, DAX queries can also be run against Analysis Services Multidimensional  models. DAX queries are often easier to write and more efficient than  Multidimensional Data Expressions (MDX) queries.

A DAX query is a statement, similar to a SELECT statement in T-SQL. The most basic type of DAX query is an *evaluate* statement. For example,

​		DAX 	 	

```dax
EVALUATE
 ( FILTER ( 'DimProduct', [SafetyStockLevel] < 200 ) )
ORDER BY [EnglishProductName] ASC
```

Returns in Results a table listing only those products with a  SafetyStockLevel less than 200, in ascending order by  EnglishProductName.





# References

* https://learn.microsoft.com/en-us/dax/dax-overview