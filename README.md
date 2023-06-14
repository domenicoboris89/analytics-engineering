# analytics-engineering
Building a Dimensional Data Warehouse using dbt and BigQuery


## dbt installation

0. Install __pyenv__ to manage Python versions and virtual environments: https://github.com/pyenv/pyenv 

1. Create a new Python environment for the dbt and its big query adapter:<br> 
    `pyenv virtualenv dbt-bigquery`

2. To install `dbt-core` and `dbt-bigquery`:<br>

    `pip install \
        dbt-core \
        dbt-bigquery \
    `

