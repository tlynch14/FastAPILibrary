# Getting Started

## venv
`python -m venv env`
`pip install fastapi fastapi-sqlalchemy pydantic alembic uvicorn python-dotenv psycopg2`

Issue with alembic - investigation required.

## Docker 
`docker-compose build`
`docker-compose up`

`docker-compose run app alembic revision --autogenerate -m "New Migration"`
`docker-compose run app alembic upgrade head`

## Setup

We need to connect pgAdmin to our db

### PgAdmin

5050: pgAdmin Area
See `.env` for credentials


## Tooling Explained

1. Uvicorn: Simple Server
2. SQLAlchemy: ORM DB toolkit (Can use standard Python classes - requires `fastapi-sqlachemy`) 
3. Alembic: DB Migrator, foils with SQLAlchemy.
    -  To run migration `docker-compose run app alembic revision --autogenerate -m "New Migration"`
    - To push migration `docker-compose run app alembic upgrade head`