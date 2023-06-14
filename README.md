# analytics-engineering
Building a Dimensional Data Warehouse using dbt and BigQuery.<br>

This repository contains a step-by-step build up of a `dbt-bigquery` project.<br> 
The folder __DL_NORTHWIND__ contains the dataset to model on dbt, while the other folder is the name of the dbt project.

## dbt installation


0. Install __pyenv__ to manage Python versions and virtual environments: https://github.com/pyenv/pyenv 


1. Create a new Python environment for the dbt and its big query adapter:<br> 

    `pyenv virtualenv dbt-bigquery`

    and upgrade pip:

    `pip install --upgrade pip`


2. Install __dbt-core__ and __dbt-bigquery__:<br>

    `pip install \ dbt-core \ dbt-bigquery \`<br>
    
    and check the version:

    `dbt --version`<br>

    ![Alt text](image.png)


3. Initialize the dbt project and assign it a valid name. In this use case, the name is "NT_DWH" as per Northwind Traders Data Warehouse:<br>

    - run `dbt init NT_DWH`

    - choose __bigquery__ as db

    - choose __oauth__ as authenthication method

    - add your GCP project_id


