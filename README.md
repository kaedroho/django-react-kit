<h1 align="center">
    Django React Kit
</h1>

<p align="center">
    <br>
    <a href="https://opensource.org/licenses/BSD-3-Clause">
        <img src="https://img.shields.io/badge/license-BSD-blue.svg" alt="License" />
    </a>
</p>

Django React Kit is a template for rapidly building applications with Django and React.

## What's included

 - A Django project with Poetry
 - A React frontend with Vite and eslint
 - Docker compose to help run it all in development
 - Dockerfile for building a deployable container

## Starting a new application

Make sure you have an up-to-date version of [Node.js](https://nodejs.org/) installed and your current working directory is the one where you intend to create a project.

Run the following command in your command line:

```sh
npm create django-react@latest
```

This command will install and execute [`create-django-react`](https://www.npmjs.com/package/create-django-react).

### Running the new project with Docker Compose

The root folder contains a ``docker-compose.yml`` file  and ``Makefile`` containing some shortcuts for docker compose.

To create the Docker environment, run ``make setup``. Once that's finished, run ``make start`` to boot it up.

Your new project should be running on [localhost:8000](http://localhost:8000)!

### Running the new project without Docker Compose

You will need to open two terminals so that you can run the Python and Vite processes side by side.

In one terminal, run the following commands to start the Vite devserver:

```sh
cd client
npm install
npm run dev
```

This should start a server at [localhost:5173](http://localhost:5173), there shouldn't be anything here as this will be used by the Python server to fetch built JavaScript in development.

In the other terminal, run the following to install Django, create the database, create a user, then start the Django devserver:

```sh
cd server
poetry install
poetry run python manage.py migrate
poetry run python manage.py createsuperuser
poetry run python manage.py runserver
```

Your new project should be running on [localhost:8000](http://localhost:8000)!

## Support

For support, please reach out to us on [GitHub discussions](https://github.com/kaedroho/django-react-kit/discussions)
