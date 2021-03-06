# Bigquery-Streamlit

This project demonstrates running SQL queries on [BigQuery](https://cloud.google.com/bigquery/) public datasets and rendering results into an interactive [Streamlit](https://streamlit.io) app. 

Blog post: https://imadelhanafi.com/posts/bigquery_dashboard/

Live version: https://bigquery.imadelhanafi.com


<a href="https://nlp.imadelhanafi.com">
<img src="https://imadelhanafi.com/data/draft/app.png" width="800" height="450" class="center"/>
</a>

# Running on cloud/local machine

To run the application, build the docker image and run it using the following commands

```
docker build -t app .
```

```
docker run --rm -p 8080:8080 app:latest
```

The application will be available on http://0.0.0.0:8080. 

**Note:**
In order to use BigQuery API in python, we need to create a credential file (JSON file) and declare its path as an environment variable `GOOGLE_APPLICATION_CREDENTIALS` (by default defined in `modules/data_query.py`). 
To create the credential file follow steps explained here: https://cloud.google.com/bigquery/docs/quickstarts/quickstart-client-libraries


# Code

- `app.py` : Streamlit script to define the UI. 

Modules: 

- `modules/data_query.py`: Define Data fetcher from BigQuery (takes an SQL command and return results in Pandas DataFrame).

- `modules/sql_queries.py`: Pre-defined parametrized SQL commands. 

- `modules/utils.py`: Contains a function to run queries concurrently (multi-threading) and a function to compute size of data anluzed by a given query. 

- `modules/plot.py`: Plot functions. 


--- 
By Imad 
https://imadelhanafi.com
