# analytics-engineering
Building a Dimensional Data Warehouse using dbt and BigQuery


## dbt installation

0. Install __pyenv__ to manage Python versions and virtual environments: https://github.com/pyenv/pyenv 

1. Create a new Python environment for the dbt and its big query adapter:<br> 

    `pyenv virtualenv dbt-bigquery`

    and upgrade pip:

    `pip install --upgrade pip`

2. Install __dbt-core__ and __dbt-bigquery__:<br>

    `pip install \ dbt-core \ dbt-bigquery \`<br>
    
    `dbt --version`
    ![Alt text](image.png)

3. Initialize the dbt project:<br>

    `dbt init`

