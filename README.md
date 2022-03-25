## Testing dbt project: `jaffle_shop`

`jaffle_shop` is a fictional ecommerce store. This dbt project transforms raw data from an app database into a customers and orders model ready for analytics.

### What is this repo?
A playground for updating source configs related to [#3662](https://github.com/dbt-labs/dbt-core/issues/3662)

### What's in this repo?
This repo contains [seeds](https://docs.getdbt.com/docs/building-a-dbt-project/seeds) that includes some (fake) raw data from a fictional app.

The raw data consists of customers, orders, and payments.


### Running this project
To get up and running with this project:
1. set an environment variable to point to the committed profile.  The default is ~/.dbt/profile.yml but this way the file can be committed.  It uses the same docker container as the `dbt-core` test suite.

```
$ export DBT_PROFILES_DIR=~/Projects/source_config_project
```

2. Ensure your profile is setup correctly from the command line:
```bash
$ dbt debug
```
3. Install the local dependency
```bash
$ dbt deps
```

4. Load the CSVs with the demo data set. This materializes the CSVs as tables in the dbt_sources schema. This makes it easier for the soucres to be generated in another schema without special commands.
```bash
$ cd generate_sources
$ dbt seed
```

