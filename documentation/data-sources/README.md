#  Data sources

## 1. **Overview**

- **Data Source Name**: A unique, descriptive name for the data source.
- **Purpose**: A brief description of the data source’s purpose and role in the overall system or dataset (e.g., “This dataset contains customer transaction data from the online store”).
- **Data Source Owner**: The person or team responsible for maintaining the data source.
- **Access**: Where the data source can be found (e.g., database name, file path, API endpoint, etc.) and who has access to it.

### 2. **Data Source Type**

- **Type**: Identify whether the data source is a database, flat file (e.g., CSV, JSON, XML), API, or something else.
- **Location**: Server, cloud storage, local disk, etc.
- **Connection Details**: For databases, include connection string details, user access permissions, etc. For APIs, include endpoints, authentication, and rate limits.
- **Data Update Frequency**: How often the data is updated (e.g., daily, weekly, real-time, etc.).

### 3. **Data Structure**

- **Schema/Metadata**: Provide the schema or layout of the data, describing all the tables, fields, or data objects. Include data types for each field (e.g., `integer`, `string`, `datetime`).
- **Relationships**: If applicable, describe the relationships between different datasets, tables, or collections (e.g., foreign keys, many-to-one relationships).
- **Example Records**: Include some example records to show what the data looks like, including sample values.

### 4. **Field Definitions**

- **Field Name**: The name of the field/column in the dataset.
- **Description**: A brief explanation of what each field represents.
- **Data Type**: The data type (e.g., integer, string, boolean, datetime).
- **Nullable**: Whether the field can contain `NULL` values.
- **Allowed Values/Range**: If applicable, specify any valid values or ranges for a field (e.g., a column that only allows certain statuses like "Active", "Inactive").
- **Example Value**: Provide sample values to make the meaning of the field clearer.

### 5. **Data Quality**

- **Data Accuracy**: Provide any known issues with the accuracy of the data (e.g., missing records, outdated information, known anomalies).
- **Completeness**: Indicate whether the dataset is complete or if there are missing values, and how to handle them.
- **Consistency**: Highlight any inconsistencies in the data, such as different formats, units, or values that could create problems.
- **Data Cleaning Rules**: If there are any known data cleaning rules or transformations (e.g., removing outliers, filling missing values), list them here.

### 6. **Data Lineage**

- **Origin**: Where the data is coming from (e.g., data entry, external systems, or sensors).
- **Transformation**: Document any transformations or calculations applied to the data (e.g., how raw data is aggregated or formatted).
- **Destination**: Describe where the data ends up (e.g., reporting tools, BI dashboards, etc.).
- **Update History**: If the data source has been modified over time, document any key changes.

### 7. **Usage Notes**

- **Intended Users**: Specify who is the primary user of the data (e.g., business analysts, developers, data scientists).
- **Business Rules**: Outline any business-specific rules or logic that applies to the data (e.g., how to interpret certain columns or calculated fields).
- **Important Constraints**: Mention any constraints on how the data can be used, like privacy policies, access restrictions, or legal/regulatory concerns.

### 8. **Sample Queries/Use Cases**

- **Common Queries**: Provide common SQL queries, API calls, or other methods to extract data from the source.
- **Use Cases**: Examples of how the data is used in analysis or reports.

### 9. **Versioning & Change History**

- **Version Control**: If the data source has multiple versions or updates, track changes and updates to the data structure, business rules, or other important elements.
- **Change Log**: A record of major changes made to the data source over time (e.g., new fields added, fields removed, schema changes, etc.).

### 10. **Security & Access Control**

- **Data Sensitivity**: Describe any sensitive data (e.g., PII, financial data) and how it’s protected (e.g., encryption, anonymization).
- **Access Control**: Define who has access to the data and any access restrictions.
- **Auditing**: If relevant, include how the data is audited for access or changes.

### 11. **Troubleshooting**

- **Known Issues**: Document any issues that users might encounter (e.g., outdated data, missing data) and the steps to resolve them.
- **Support Contacts**: Who to contact if there’s a problem with the data.



## Example - General data sources

 

| **Source Name**              | **Type**       | **Location**                                    | **Refresh Method** | **Contact**              |
| ---------------------------- | -------------- | ----------------------------------------------- | ------------------ | ------------------------ |
| **Sales DB**                 | SQL            | server.database.windows.net                     | Gateway            | IT DBA                   |
| **Marketing Data**           | Excel          | C:\Users\Marketing\Documents\Report.xlsx        | Import             | Marketing Team           |
| **Customer CRM**             | SQL Server     | crm.company.com                                 | DirectQuery        | CRM Admin                |
| **Employee Info**            | SharePoint     | https://company.sharepoint.com/sites/employees  | Scheduled Refresh  | HR Dept                  |
| **Web Logs**                 | CSV            | C:\Data\Logs\web_logs.csv                       | Import             | Web Team                 |
| **Google Analytics**         | Online Service | analytics.google.com                            | API Refresh        | Marketing Team           |
| **Product Inventory**        | MySQL          | inventory.company.com                           | Gateway            | IT Support               |
| **Order Data**               | PostgreSQL     | orders.company.com                              | DirectQuery        | Sales Team               |
| **Customer Support**         | Zendesk        | zendesk.company.com                             | API Refresh        | Customer Support         |
| **Employee Payroll**         | SQL            | server.database.local                           | Scheduled Refresh  | HR Dept                  |
| **Social Media Data**        | Facebook       | facebook.com/insights                           | Scheduled Refresh  | Social Media Team        |
| **Financial Reports**        | Excel          | C:\Users\Finance\Documents\fin_reports.xlsx     | Import             | Finance Team             |
| **Project Tracker**          | SharePoint     | https://company.sharepoint.com/sites/projects   | Scheduled Refresh  | Project Management       |
| **Sales Performance**        | Google Sheets  | https://docs.google.com/spreadsheets/sales_data | Import             | Sales Team               |
| **Customer Feedback**        | SurveyMonkey   | api.surveymonkey.com                            | API Refresh        | Customer Experience Team |
| **Databricks Sales Data**    | Databricks     | https:///sql/warehouse                          | DirectQuery        | Databricks Admin         |
| **Databricks Customer Data** | Databricks     | https:///sql/warehouse                          | DirectQuery        | Databricks Admin         |





## Example Template for Data Source Documentation:

------

#### **Data Source: Sales Transactions Database**

- **Purpose**: Contains all transactions made through the online store, including customer details, products purchased, and payment information.
- **Owner**: Data Management Team
- **Access**: Database hosted on `sales-db.company.com`. Access granted via VPN for authorized personnel.

------

**Schema**

| Table Name   | Field Name     | Data Type | Description                       |
| ------------ | -------------- | --------- | --------------------------------- |
| transactions | transaction_id | INTEGER   | Unique identifier for each sale.  |
| transactions | customer_id    | INTEGER   | Unique identifier for customers.  |
| transactions | amount         | DECIMAL   | Total purchase amount.            |
| transactions | date           | DATETIME  | Date and time of the transaction. |
| customers    | customer_name  | STRING    | Name of the customer.             |
| customers    | email          | STRING    | Email address of the customer.    |

------

**Data Quality**

- **Accuracy**: Customer email addresses may sometimes be missing or invalid.
- **Completeness**: Transaction records are 99% complete, but occasionally, there are cases of failed payments.
- **Consistency**: All monetary fields use two decimal places; dates are standardized in UTC format.

------

**Sample Query**

```sql
SELECT customer_name, SUM(amount) as total_spent
FROM transactions t
JOIN customers c ON t.customer_id = c.customer_id
WHERE t.date BETWEEN '2023-01-01' AND '2023-12-31'
GROUP BY customer_name
ORDER BY total_spent DESC;
```

------

**Security**

- **Data Sensitivity**: Contains sensitive information like customer PII and transaction details.
- **Access Control**: Only authorized personnel from the Data Management and Business Intelligence teams have access.

------

  



 

| **Source Name**              | **Type**       | **Location**                                    | **Refresh Method** | **Contact**              |
| ---------------------------- | -------------- | ----------------------------------------------- | ------------------ | ------------------------ |
| **Sales DB**                 | SQL            | server.database.windows.net                     | Gateway            | IT DBA                   |
| **Marketing Data**           | Excel          | C:\Users\Marketing\Documents\Report.xlsx        | Import             | Marketing Team           |
| **Customer CRM**             | SQL Server     | crm.company.com                                 | DirectQuery        | CRM Admin                |
| **Employee Info**            | SharePoint     | https://company.sharepoint.com/sites/employees  | Scheduled Refresh  | HR Dept                  |
| **Web Logs**                 | CSV            | C:\Data\Logs\web_logs.csv                       | Import             | Web Team                 |
| **Google Analytics**         | Online Service | analytics.google.com                            | API Refresh        | Marketing Team           |
| **Product Inventory**        | MySQL          | inventory.company.com                           | Gateway            | IT Support               |
| **Order Data**               | PostgreSQL     | orders.company.com                              | DirectQuery        | Sales Team               |
| **Customer Support**         | Zendesk        | zendesk.company.com                             | API Refresh        | Customer Support         |
| **Employee Payroll**         | SQL            | server.database.local                           | Scheduled Refresh  | HR Dept                  |
| **Social Media Data**        | Facebook       | facebook.com/insights                           | Scheduled Refresh  | Social Media Team        |
| **Financial Reports**        | Excel          | C:\Users\Finance\Documents\fin_reports.xlsx     | Import             | Finance Team             |
| **Project Tracker**          | SharePoint     | https://company.sharepoint.com/sites/projects   | Scheduled Refresh  | Project Management       |
| **Sales Performance**        | Google Sheets  | https://docs.google.com/spreadsheets/sales_data | Import             | Sales Team               |
| **Customer Feedback**        | SurveyMonkey   | api.surveymonkey.com                            | API Refresh        | Customer Experience Team |
| **Databricks Sales Data**    | Databricks     | https:///sql/warehouse                          | DirectQuery        | Databricks Admin         |
| **Databricks Customer Data** | Databricks     | https:///sql/warehouse                          | DirectQuery        | Databricks Admin         |

