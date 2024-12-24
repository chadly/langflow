# Langflow Project Template

This repository is a project template for a [LangFlow](https://www.langflow.org/) project runnable via `docker compose`.

It will spin up langflow along with a [postgres database](https://www.postgresql.org/) and a [pgAdmin instance](https://www.pgadmin.org/) to access it.

## Running Locally

Clone this repository directly or create a repo from [GitHub's repository template feature](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template).

Create a local copy of the environment variables file:

```
cp .env.example .env
```

and modify the values to your heart's content. These values can be made available within the containers specified in `docker-compose.yml`.

From there, you can run the containers via `docker compose` directly:

```
docker compose up
```

### Accessing Langflow

Access LangFlow at [localhost:7860](http://localhost:7860/).

### Accessing pgAdmin

Access [localhost:8420](http://localhost:8420/) with the username/password specified in `.env`. From there, you can register a new server:

| Category     | Setting           | Value                |
|--------------|-------------------|----------------------|
| General      | Name              | local                |
| Connection   | Host name/address | db                   |
| Connection   | Port              | 5432                 |
| Connection   | Username          | ${POSTGRES_USER}     |
| Connection   | Password          | ${POSTGRES_PASSWORD} |
| Connection   | Save Password     | Yes                  |

The values `POSTGRES_USER` and `POSTGRES_PASSWORD` are defined and can be changed in `.env`.
