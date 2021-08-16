# Postgres-Jupyter-Notebook-Microservice

Postgres &amp; Jupyter Notebook MicroserviceTemplate for DataScience / DataEngineering ETL tests.

- [About](#about)
- [Tech/Framework used](#tech/framework-used)
- [Features](#features)
- [Deployment](#deployment)
- [API Reference](#api-reference)

## Motivation

The Project was started in order to quickly develop and test ETL piplines. After installing Docker the User can immediately spin up postgres and jupyter notebook container using docker-compose.

## Tech/Framework used

- Docker
- Jupyter Notebook
- Postgres

## Features

- The Jupyter Notebook is automatically connected to the Postgres Database.
- You can set/edit Postgres Credentials in the .env file. It will automatically be used in the jupyter notebook.
- The local directory is bound to the jupyter notebook container. Any file you create via Jupyter notebook in the Jupyter container will be available in the workspace folder.

## Deployment

Please install docker.
[Docker](https://www.docker.com/)

## API Reference

### Build the containers

```cmd

docker-compose build

```

### Start the containers

```cmd

$ docker-compose up

...
...
 or http://127.0.0.1:8888/?token=xxxxxxxxxxxxxxxxxxxxx

```

Docker compose will spin up two containers:

- sparkifydb (the postgres database)
- jupyter (jupyter notebook container)

Jupyter displays multiple links to start working in the browser. Use the last one with "http://127.0.0.1:8888/?token=xxxxx

### Running a python script in a container

```cmd

docker-compose run --rm jupyter_notebook python name_of_my_script.py

```

### Opening python interactively in the shell

```cmd

docker-compose run --rm jupyter_notebook python

```

### Opening an interactive bash shell

```cmd

docker-compose run --rm jupyter_notebook bash

```

### Adding python packages

Add python packages to the jupyter notebook container by adding them to the requirements.txt file.
After adding the packages don't forget to rebuild the container.

```cmd

docker-compose up --build

```

## Credits

This project has been inspired by [Udacity Data Engineering nanodegree](https://www.udacity.com/course/data-engineer-nanodegree--nd027),
with the aim to build the full microservice infrastructure on my own.

Helpfull documentation and resources:

- [Docker Documentation](https://docs.docker.com/)
- [Jupyter Docker Stacks](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/recipes.html)

## License

MIT © [Etienne Schmelzer](https://github.com/EtienneEs/)
