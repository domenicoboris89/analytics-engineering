# analytics-engineering 
Building a Dimensional Data Warehouse using dbt and BigQuery.<br>
![Alt text](/png/dbt-Core-Bigquery-Blog-Image.png)


## Navigation


This repository contains the Use Case of a Dimensional DWH build using `dbt` and `bigquery`, it contains two folders: <br> 

1. The folder __DL_NORTHWIND__ contains the dataset to model on dbt

2. the other folder is the name assigned to the dbt project, in this case __NT_DWH__


## dbt installation


0. Install __pyenv__ to manage Python versions and virtual environments: https://github.com/pyenv/pyenv 


1. Create a new Python environment for the dbt and its big query adapter:<br> 


        pyenv virtualenv dbt-bigquery


2. Install __dbt-core__ and __dbt-bigquery__:<br>


        pip install --upgrade pip
        pip install dbt-core
        pip install dbt-bigquery

    
    and check the version:<br>


        dbt --version


    that should be the output message:<br>
    ![Alt text](  /png/dbt%20version.png)


4. Initialize the dbt project and assign it a valid name. In this use case, the name is "NT_DWH" as per Northwind Traders Data Warehouse:<br>


    - run `dbt init NT_DWH`
    - choose __bigquery__ as database type
    - choose __oauth__ as authenthication method
    - add your GCP __project_id__


5. Now execute `dbt debug` and complete the configuration of your `profiles.yml` with the connections to the Database   


        ~/.dbt/profiles.yml
            my-bigquery-db:
                target: dev
                outputs:
                    dev:
                    type: bigquery
                    method: oauth
                    project: [GCP project id]
                    dataset: [the name of your dbt dataset] # You can also use "schema" here
                    threads: [1 or more, number of parallelism in the tasks execution]
                    <optional_config>: <value>


Setup the gcp oauth using gcloud: https://docs.getdbt.com/docs/core/connect-data-platform/bigquery-setup#local-oauth-gcloud-setup <br>

__gcloud authentication command__:


        gcloud auth application-default login \
        --scopes=https://www.googleapis.com/auth/bigquery,\
        https://www.googleapis.com/auth/drive.readonly,\
        https://www.googleapis.com/auth/iam.test


6. If you work with multiple warehouses you need to tell dbt which `profiles.yml` to use. There are several ways to do that, for more info check the official documentation: https://docs.getdbt.com/docs/core/connect-data-platform/connection-profiles.<br>
One possibility is to use the the `--profiles-dir` flag every time you execute a dbt command, followed by 'path/to/directory'.<br>


That's how a well configured dbt project, looks like:


![Alt text](/png/dbt%20debug.png)

