# SCD Type 2 & Data Quality Pipeline

An incremental SSIS pipeline that loads employee data from an operational source into a historical warehouse while tracking changes and data-quality KPIs.

## Pipeline

The package:

- loads employee data from CSV into an operational SQL Server table;
- enriches employee records with city names;
- calculates derived fields such as employee age;
- compares operational data with the historical warehouse;
- inserts new employees and preserves updates using **Slowly Changing Dimension Type 2** logic;
- records field-level changes in an audit table;
- calculates completeness KPIs after updates;
- logs processing errors;
- exports operational, DWH, KPI, log, and error tables to CSV.

The control flow includes a loop designed to repeat the incremental process at one-minute intervals.

## Data Quality Metrics

Two completeness-oriented measures are calculated:

- **Defected Records** — percentage of employee rows containing at least one missing value.
- **Defected Data Items** — percentage of missing cells across the employee dataset.

## Key Concepts

- Incremental ETL
- SCD Type 2
- Historical change tracking
- Audit logging
- Data-quality KPIs
- Derived columns
- Repeated / scheduled-style processing

## Expected Working Path

```text
C:\Data
```

## Files

```text
scd2_data_quality_pipeline.sln
scd2_data_quality_pipeline/
├── scd2_data_quality_pipeline.dtproj
├── Package.dtsx
└── Project.params
```
