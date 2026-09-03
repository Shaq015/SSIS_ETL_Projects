# Operational Database & Data Warehouse Pipeline

An SSIS project that builds an operational database, populates it with data, and loads a dimensional data warehouse for analytical use.

## Pipeline

The package contains two main control-flow sequences:

- **Operational database initialization**
  - creates the source database tables;
  - loads `USERS`, `EQUIPMENTS`, `EXERCISES`, `PROGRAMS`, `DAYPLANS`, and `CONTENTS`;
  - preserves the dependency order between related entities.

- **Data warehouse creation and loading**
  - creates the warehouse tables;
  - loads the `USER_D` and `EXERCISE_D` dimensions;
  - loads the `DETAILS_F` fact table from the operational model;
  - uses joins, lookups, aggregation, and derived calculations to enrich fact-level records.

The fact-processing logic includes measures related to membership, registration, supplements, equipment, delivery, actual repetitions, pulse, and burned calories.

## Key Concepts

- Operational-to-analytical ETL
- Dimensional modeling
- Dimension and fact loading
- Merge Join / Lookup
- Multicast and Aggregate
- Derived fact calculations
- SQL Server destinations

## Files

```text
operational_data_warehouse.sln
operational_data_warehouse/
├── operational_data_warehouse.dtproj
├── Package.dtsx
└── Project.params
```

## Running

Open the solution in Visual Studio, update the `localhost` SQL Server connection to your environment, and run `Package.dtsx`.
