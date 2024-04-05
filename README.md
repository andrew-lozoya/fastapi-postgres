# FastAPI-Postgres

This REST API, originally authored by @jod35, has been enhanced to incorporate New Relic Python instrumentation. It serves as a demonstration of utilizing FastAPI with Async SQLAlchemy and PostgreSQL. Original credits can be found in [this video](https://youtu.be/nC9ob8xM3AM).

## Running the Code Locally
- Set up a ```DATABASE_URL``` environment variable as follows and ensure that this URI is a ```postgresql+asyncpg``` schema database string.
```
postgresql+asyncpg://sally:sallyspassword@dbserver.example:5555/userdata
    ^                 ^         ^               ^           ^     ^
    |- schema         |         |- password     |- host     |     |
                      |                                     |     |
                      |- username                           |     |- database
                                                            |
                                                            |- port
```

- Add the following system environment variables: ```NEW_RELIC_LICENSE_KEY=INSERT_YOUR_LICENSE_KEY``` and ```NEW_RELIC_APP_NAME=INSERT_YOUR_APP_NAME```.
- Install all project dependencies listed in the ```requirements.txt``` file using ```pip install -r requirements.txt```.
- Create the necessary database tables by executing ```python create_db```.
- Finally, start your server with ```newrelic-admin run-program uvicorn main:app --host=0.0.0.0 --port 8080```.
