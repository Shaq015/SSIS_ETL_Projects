# Dynamic Multi-Source Transformation

An SSIS pipeline for processing a daily compressed delivery containing heterogeneous data sources and loading transformed records into SQL Server.

## Pipeline

The package:

- creates and manages dynamic staging folders;
- locates and extracts the daily ZIP payload;
- processes `Supplier`, `Product`, `Hotel`, and `Employee` CSV data;
- enriches employee records with company information from a separate text source;
- loads transformed data into SQL Server tables;
- deletes processed intermediate files;
- archives the original compressed delivery;
- logs errors and exports them to CSV.

The implementation uses variables and expressions so folder names and locations can be changed without redesigning the control flow.

## Key Concepts

- Multi-source ETL
- Dynamic staging
- ZIP extraction
- Flat-file transformations
- Cross-source enrichment
- Error handling and logging
- Archiving and cleanup
- Parameterized paths

## Expected Working Path

```text
C:\Staging\
├── SharingFolder\
├── ProcessFolder\
└── ArchivedFolder\
```

## Files

```text
dynamic_multi_source_etl.sln
dynamic_multi_source_etl/
├── dynamic_multi_source_etl.dtproj
├── Package.dtsx
└── Project.params
```
