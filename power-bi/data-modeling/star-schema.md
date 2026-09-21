

# Understand star schema and the importance for Power BI

## Star schema overview

*Star schema* is a mature modeling approach widely adopted by relational data warehouses. It requires modelers to classify their model tables as either *dimension* or *fact*.



### Dimension tables

*Dimension tables* describe business entities—the *things* you model. Entities can include products, people, places, and concepts including time itself. The most consistent table you'll find in a star schema is a date dimension table. A dimension table contains a key column (or columns) that acts as a unique identifier, and other columns. Other columns support filtering and grouping your data.



### Fact tables

*Fact tables* store observations or events, and can be sales orders, stock balances, exchange rates, temperatures, and more. A fact table contains dimension key columns that relate to dimension tables, and numeric measure columns. The dimension key columns determine the *dimensionality* of a fact table, while the dimension key values determine the *granularity* of a fact table. For example, consider a fact table designed to store sale targets that has two dimension key columns `Date` and `ProductKey`. It's easy to understand that the table has two dimensions. The granularity, however, can't be determined without considering the dimension key values. In this example, consider that the values stored in the `Date` column are the first day of each month. In this case, the granularity is at month-product level.

Generally, dimension tables contain a relatively small number of rows. Fact tables, on the other hand, can contain a large number of rows and continue to grow over time.

![Diagram showing an illustration of a star schema.](https://learn.microsoft.com/en-us/power-bi/guidance/media/star-schema/star-schema-example-1.svg)



## Normalization vs. denormalization

To understand some star schema concepts described in this article, it's important to know two terms: normalization and denormalization.

*Normalization* is the term used to describe data that's stored in a way that reduces repetitious data. Consider a table of products that has a unique key value column, like the product key, and other columns that describe product characteristics, like product name, category, color, and size. A sales table is considered normalized when it stores only keys, like the product key. In the following image, notice that only the `ProductKey` column records the product.

![Diagram showing a table of data that includes a Product Key column.](https://learn.microsoft.com/en-us/power-bi/guidance/media/star-schema/normalized-data-example.svg)

If, however, the sales table stores product details beyond the key, it's considered *denormalized*. In the following image, notice that the `ProductKey` and other product-related columns record the product.

![Diagram showing a table of data that includes a Product Key and other product-related columns, including Category, Color, and Size.](https://learn.microsoft.com/en-us/power-bi/guidance/media/star-schema/denormalized-data-example.svg)

When you source data from an export file or data extract, it's likely that it represents a denormalized set of data. In this case, use [Power Query](https://learn.microsoft.com/en-us/training/modules/clean-data-power-bi/) to transform and shape the source data into multiple normalized tables.

As described in this article, you should strive to develop optimized Power BI semantic models with tables that represent normalized fact and dimension data. However, there's one exception where a [snowflake dimension](https://learn.microsoft.com/en-us/power-bi/guidance/star-schema#snowflake-dimensions) might be denormalized in order to produce a single model table.



# References

* [Understand star schema and the importance for Power BI](https://learn.microsoft.com/en-us/power-bi/guidance/star-schema)
