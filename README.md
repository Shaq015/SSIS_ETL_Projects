# SSIS ETL Projects

A collection of practical **SQL Server Integration Services (SSIS)** projects covering metadata-driven ingestion, multi-source transformation, operational-to-warehouse loading, slowly changing dimensions, data quality, logging, and error handling.

## Projects

| Project | Main Focus | Key Concepts |
|---|---|---|
| [Operational Database & Data Warehouse](./01-operational-data-warehouse/) | OLTP initialization and dimensional warehouse loading | Control Flow, Data Flow, dimensions, fact table, lookups, aggregations, derived facts |
| [Metadata-Driven File Ingestion](./02-metadata-driven-file-ingestion/) | Dynamic CSV validation and routing | Metadata comparison, Foreach Loop, variables, expressions, file routing, reporting |
| [Dynamic Multi-Source Transformation](./03-dynamic-multi-source-transformation/) | Daily ZIP/CSV ingestion from heterogeneous sources | Dynamic paths, extraction, joins, transformations, SQL Server loading, archiving, error logging |
| [SCD Type 2 & Data Quality](./04-scd2-data-quality/) | Incremental OLTP-to-DWH processing | SCD Type 2, change tracking, audit logging, completeness KPIs, scheduled-style incremental flow |

## Repository Structure

```text
SSIS_ETL_Projects/
├── 01-operational-data-warehouse/
├── 02-metadata-driven-file-ingestion/
├── 03-dynamic-multi-source-transformation/
├── 04-scd2-data-quality/
├── README.md
└── .gitignore
```

Each project contains the Visual Studio solution, SSIS project file, package source (`.dtsx`), and project parameters required to inspect and run the package.

## Technologies

- Microsoft SQL Server Integration Services (SSIS)
- SQL Server
- Visual Studio / SQL Server Integration Services Projects
- ETL / ELT
- Dimensional modeling
- Slowly Changing Dimensions (SCD)
- Data quality and audit logging
- Flat-file and multi-source ingestion

## Setup

1. Open the `.sln` file of the desired project in Visual Studio with the **SQL Server Integration Services Projects** extension installed.
2. Update the SQL Server connection manager for your environment.
3. Prepare the input files expected by that project.
4. Review the project-specific README for the expected local folders and flow.

## Security & Portability

Local machine/user identifiers from the original development environment were removed. SQL Server connection managers were sanitized to use `localhost`/`LOCALHOST\USER`; update them before execution.

The remaining paths such as `C:\Data`, `C:\Staging`, and `C:\SSIS-1` are project-specific working directories rather than personal user paths. No passwords, API keys, database credentials, compiled SSIS artifacts, Visual Studio user files, or project documents are included.
