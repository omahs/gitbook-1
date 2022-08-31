---
description: A guide to data curation with Flipside.
---

# Contribute to Flipside Data

## Public Data Models

Links to the public Github repos for all data model source code can be found in the [table docs](tables/) for each blockchain/blockchain project.

## Contribute Tags & Labels

See [How to Add Tags](https://docs.flipsidecrypto.com/our-data/data-models/tags#how-to-add-tags) on the Tags data model page.

## Contribute Models with DBT

The Flipside community uses [DBT](https://docs.getdbt.com/) to model data. This section gives a complete overview of getting set up to contribute models with DBT. (Hint: if you know SQL, you're 95% of the way to knowing DBT.) [Avalanche](tables/avalanche-tables.md) and [Ethereum ](tables/ethereum-core-tables.md)repositories are setup for community curation.

#### Access

**Snowflake (ask in #community-curation-beta discord channel)**

"Hi , I’m interested in doing data curation for Flipside, could you give me snowflake access please? I’d like my username to be:  `community_<insert_username>"`

**dbt cloud \[Optional]**

Sign up on your own:  [https://www.getdbt.com/signup/](https://www.getdbt.com/signup/)

#### **Software Setup**

* (Optional) Install dbt on your terminal:[  https://docs.getdbt.com/dbt-cli/install/overview](https://docs.getdbt.com/dbt-cli/install/overview)
* Install Git (if you don’t have it):[  https://git-scm.com/book/en/v2/Getting-Started-Installing-Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* Download Docker desktop: [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)
* Install VSCode: [https://code.visualstudio.com/download](https://code.visualstudio.com/download)

#### **Project Setup**

1. Clone the project you want to work on from [FlipsideCrypto Github Org](https://github.com/FlipsideCrypto)
   * Example for Ethereum: `git clone https://github.com/FlipsideCrypto/ethereum-models.git`
2. Open the project in VSCode
3. Create a `.env` file in the root directory of your project (note: the .env file will not be committed to the source)
   * There is a provided `.env.sample` in the repository you may use as reference to create `.env`
4. Start a new branch in the repository
   * Ensure you have the latest pulled down from the `main` branch
     * `git checkout main`
     * `git pull`
   * Branch name should follow convention:  `community/<branch_name>`
   * Ex:  `git checkout -b community/my-new-model`
5. Start dbt console (this is where you will run your models to have them deployed to snowflake)
   * `make dbt-console`
6. Within the console, run `dbt debug` to ensure all connections are working

**You are now ready to create your first data model!**

#### **Create and contribute your first model**

1. Understand the modeling structure
   * Data models iterate through different “layers”. Generally speaking these are bronze, silver, and core.
   * Bronze is raw data layer
   * Silver is intermediate data modeling layer
   * Core is the presentation layer, aka what is exposed to the public
   * **Most of the time you will be working within the silver layer**
2. Create model file within the proper layer and naming convention
   * Naming convention for file is `<layer name>__<table name>.sql`
   * Example for silver layer: **** `./models/silver/silver__my_new_table.sql`
3. Create a corresponding .yml file
   * This should hold any model/column descriptions and tests for the model/columns
   * Example for silver layer: **** `./models/silver/silver__my_new_table.yml`
4. Start writing SQL code
   * Write code in Snowflake Web UI (Snowsight):  [https://app.snowflake.com/us-east-1/vna27887](https://app.snowflake.com/us-east-1/vna27887)
   * Snowsight documentation:  [https://docs.snowflake.com/en/user-guide/ui-snowsight.html](https://docs.snowflake.com/en/user-guide/ui-snowsight.html)
5. Turn SQL code into DBT SQL
   * dbt combines sql with Jinja, see more:[ https://docs.getdbt.com/docs/building-a-dbt-project/jinja-macros](https://docs.getdbt.com/docs/building-a-dbt-project/jinja-macros)
   * Copy sql code into the file created earlier
   * Add config section
     * See existing models for examples
     * Dbt docs for available configurations [https://docs.getdbt.com/reference/resource-configs/snowflake-configs](https://docs.getdbt.com/reference/resource-configs/snowflake-configs)
   * Convert SQL elements into Jinja
     * Commonly this is changing table name to references and adding incremental loading logic
     * Ref: [https://docs.getdbt.com/reference/dbt-jinja-functions/ref](https://docs.getdbt.com/reference/dbt-jinja-functions/ref)
     * Incremental logic: [https://docs.getdbt.com/docs/building-a-dbt-project/building-models/configuring-incremental-models](https://docs.getdbt.com/docs/building-a-dbt-project/building-models/configuring-incremental-models)
       1. See existing curated models for examples on how to implement incremental logic. `ethereum-models/models/silver/silver__transactions.sql`
6. Run the dbt model to put it into the community dev database. You must run this command within the dbt-console. If you have exited the console run `make dbt-console` again
   * `dbt run -s <path to model>`
   * Run: [https://docs.getdbt.com/reference/commands/run](https://docs.getdbt.com/reference/commands/run)
   * If this is your 1st time using `dbt run` in this docker container, you may need to run `dbt deps` command
   * Models will be deployed to `<BLOCKCHAIN>_COMMUNITY_DEV` database within Snowflake.  This database refreshes daily at `04:00 AM UTC`, any non-production resources will be erased.
7. Run the test file
   * `dbt test -s <path to mode>`
   * Tests: [https://docs.getdbt.com/docs/building-a-dbt-project/tests](https://docs.getdbt.com/docs/building-a-dbt-project/tests)
8. Create GitHub Pull Request and write a summary on your updates/changes, as well as attaching passing test logs
9. Request Reviewer from one of the GitHub handles below
   * austinFlipside
   * juls858
   * James-Mission
   * desmond-hui
10. Fix Review Comments
11. Re-Request Reviewer after fixing review comments
12. If your PR has been approved, merge it to production
13. **Congratulations! You’ve successfully contributed a data model!**
