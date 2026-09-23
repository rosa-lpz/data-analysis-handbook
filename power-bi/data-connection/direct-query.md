

# Direct Query

DirectQuery in Power BI lets you keep data in the source and query it at report time instead of importing it. This article explains when to use DirectQuery, its limitations, and alternatives such as hybrid tables, Direct Lake, and live connections so you can choose the right mode.

## Quick decision guide

The following table summarizes which Power BI connectivity mode to consider based on your requirements. Use it as a quick reference to help choose between Import, DirectQuery, Hybrid tables, Direct Lake, or live connections:



| If you need                                                  | Consider first                                         | Why                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------ | ------------------------------------------------------- |
| Maximum interactivity and full transformation flexibility    | Import                                                 | In-memory columnar engine and rich modeling features    |
| Near real-time changes on recent fact data plus historical context | Hybrid table (Import and DirectQuery partition)        | Queries source for hot data and caches historical data. |
| Large lakehouse or warehouse scale with low latency reads (Fabric) | Direct Lake                                            | Bypasses scheduled refresh and retains Import behaviors |
| Federated access to multiple external sources without full ingestion | DirectQuery (composite model)                          | Leaves data in place and blends sources.                |
| Central governed enterprise model already published          | Live connection to semantic model or Analysis Services | Reuses curated model and avoids duplication.            |
| Push parameters to source at runtime (user-driven filtering) | DirectQuery with dynamic M parameters                  | Reduces scanned data and improves performance.          |
| High concurrency and remote latency challenges               | Import or Aggregations over DirectQuery                | Aggregations accelerate common queries                  |

# Reference

* https://learn.microsoft.com/en-us/power-bi/connect-data/desktop-directquery-about