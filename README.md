# SQL Data Warehouse

A modern data warehouse built on SQL Server Express using the Bronze, Silver, and Gold layers to ingest, cleanse, model, and report on sales data.

## Project Overview

This repository demonstrates how to design and implement a SQL Architecture data warehouse:
<img width="1155" alt="image" src="https://github.com/user-attachments/assets/05540939-663b-47e6-9666-1471211c4c40" />


- **Bronze Layer**: Stores raw CSV extracts as-is from source systems (ERP & CRM).
- **Silver Layer**: Cleanses, standardizes, and normalizes data for consistency.
- **Gold Layer**: Builds a star schema (fact and dimension tables) optimized for analytics and reporting.

The project includes:

- **ETL Pipelines**: SQL scripts (and optional Python loaders) to move data through each layer.
- **Data Modeling**: Star schema creation optimized for analytical queries.
- **Analytics & Reporting**: Sample SQL-based reports and dashboards.
- **Documentation**: Architecture diagrams, data dictionaries, and design notes.

## Repository Structure

```
|-- .github/workflows/ci.yml    # (optional) CI: SQL linting & smoke tests
|-- data
|   |-- bronze/raw_csvs         # Raw source CSV files
|   |-- silver/cleansed         # Cleaned/parquet outputs
|   `-- gold/star_schema        # Final table exports (CSV or parquet)
|-- docs
|   |-- architecture.md         # Medallion architecture details
|   |-- data_dictionary.md      # Field definitions & sources
|   `-- diagrams/               # DrawIO files & exports
|-- etl
|   |-- bronze_load.sql         # Ingest raw CSV -> staging tables
|   |-- silver_transform.sql    # Cleansing & normalization
|   `-- gold_model.sql          # Star schema creation
|-- src                         # (optional) Python/Spark ETL code
|   |-- bronze_loader.py
|   |-- silver_cleaner.py
|   `-- gold_builder.py
|-- notebooks/exploration.ipynb # Exploratory data analysis examples
|-- dashboards/                 # BI artifacts (PowerBI, Tableau files)
|-- CHANGELOG.md                # Changelog following Keep a Changelog
|-- CONTRIBUTING.md             # Contribution guidelines
|-- LICENSE                     # Project license (e.g., MIT)
|-- README.md                   # This file
`-- requirements.txt            # Python dependencies (if any)
```

## Prerequisites

- **SQL Server Express** (or Developer Edition)
- **SQL Server Management Studio (SSMS)**
- **Git** to clone the repository
- **Python 3.8+** (if using Python loaders)

## Setup & Installation

1.  **Clone the repo**
    ```bash
    git clone https://github.com/<your-username>/<repo-name>.git
    cd <repo-name>
    ```
2.  **Prepare data**
    - Place your raw CSVs in `data/bronze/raw_csvs/`.
3.  **Run Bronze ETL**
    - Open `etl/bronze_load.sql` in SSMS and execute to load staging tables.
4.  **Run Silver ETL**
    - Execute `etl/silver_transform.sql` to cleanse and populate Silver tables.
5.  **Run Gold ETL**
    - Execute `etl/gold_model.sql` to build the star schema in Gold.

> **Optional**: If you prefer Python scripts, install dependencies:
> ```bash
> pip install -r requirements.txt
> ```
> Then run:
> ```bash
> python src/bronze_loader.py
> python src/silver_cleaner.py
> python src/gold_builder.py
> ```

## Analytics & Reporting

- Sample reports and dashboards are located in `dashboards/`.
- Use provided SQL queries or BI tool files (PowerBI, Tableau) to visualize:
  - Customer behavior
  - Product performance
  - Sales trends

## Contributing

We welcome contributions! Please read `CONTRIBUTING.md` for details on:

- Opening issues
- Submitting pull requests
- Coding & documentation standards

## Changelog

See `CHANGELOG.md` for a history of changes and releases.

## License

This project is licensed under the [MIT License](LICENSE).

## Maintainer

This project is currently maintained by Chinmaya Sri Rama Seshu Pasupuleti.

Chinmaya is a Data Engineer with 4+ years of experience building enterprise data pipelines, cloud-based ETL/ELT workflows, data warehouses, and analytical data platforms.

-   **GitHub**: [Ramaseshu0](https://github.com/Ramaseshu0)
-   **LinkedIn**: [rama-seshu](https://www.linkedin.com/in/rama-seshu/)
-   **Email**: pramaseshu@outlook.com