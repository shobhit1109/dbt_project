# dbtlearn

A dbt project for analytics engineering using Snowflake as the data warehouse.

## Project Overview
This project contains dbt models, seeds, and configurations for transforming and testing data in Snowflake. It is structured for easy collaboration and scalability.

## Prerequisites
- Python 3.7+
- dbt-core and dbt-snowflake installed (`pip install dbt-core dbt-snowflake`)
- Access to a Snowflake account (with credentials)

## Setup Instructions
1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd dbtlearn
   ```
2. **Install dependencies:**
   ```bash
   pip install dbt-core dbt-snowflake
   ```
3. **Configure your dbt profile:**
   Create or edit the `profiles.yml` file in your `~/.dbt/` directory with the following template:
   ```yaml
   dbtlearn:
     target: dev
     outputs:
       dev:
         type: snowflake
         account: <account>
         user: <user>
         password: <password>
         role: <role>
         database: <database>
         warehouse: <warehouse>
         schema: <schema>
         threads: 1
         client_session_keep_alive: False
   ```
   Replace the placeholders with your Snowflake credentials.

## Project Structure
```
dbtlearn/
├── models/
│   └── src/
│       ├── src_hosts.sql
│       ├── src_reviews.sql
│       └── src_listings.sql
├── macros/         # Custom macros (currently empty)
├── seeds/          # Seed CSVs (currently empty)
├── analyses/       # Analysis files (currently empty)
├── snapshots/      # Snapshots (currently empty)
├── tests/          # Custom tests (currently empty)
├── dbt_project.yml # Project configuration
└── README.md       # Project documentation
```

## Common dbt Commands
- `dbt run` — Build models
- `dbt test` — Run tests
- `dbt seed` — Load seed data
- `dbt docs generate && dbt docs serve` — Generate and serve documentation
- `dbt clean` — Remove build artifacts

## Resources
- [dbt Documentation](https://docs.getdbt.com/docs/introduction)
- [dbt Discourse](https://discourse.getdbt.com/)
- [dbt Community Slack](https://community.getdbt.com/)
- [dbt Events](https://events.getdbt.com)
- [dbt Blog](https://blog.getdbt.com/)
