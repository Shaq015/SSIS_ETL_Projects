# Metadata-Driven File Ingestion

A dynamic SSIS ingestion pipeline that validates incoming CSV files by their metadata before loading them into SQL Server.

## Pipeline

The package:

1. iterates through files in an input directory with a **Foreach Loop Container**;
2. compares each file's column metadata against the expected schema;
3. routes compatible files to a `Processed` directory;
4. routes incompatible files to a `Wrong` directory without loading their records;
5. loads accepted rows into SQL Server;
6. generates an ETL report containing file status, record counts, and load timestamps;
7. exports the consolidated source data to CSV.

Variables and expressions are used for dynamic paths and connection strings.

## Key Concepts

- Metadata-driven ETL
- Dynamic file processing
- Foreach Loop Container
- Script Task for targeted metadata checks
- Variables and expressions
- Conditional routing
- ETL audit reporting

## Expected Working Paths

The package uses task-specific paths under:

```text
C:\SSIS-1\
├── Data\
├── Processed\
└── Wrong\
```

These paths can be changed through the package variables/expressions.

## Files

```text
metadata_driven_ingestion.sln
metadata_driven_ingestion/
├── metadata_driven_ingestion.dtproj
├── Package.dtsx
└── Project.params
```
