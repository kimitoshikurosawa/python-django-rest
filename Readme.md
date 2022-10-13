Sample Django application

## Setup

The first thing to do is to clone the repository:

```sh
$ git clone git clone https://github.com/kimitoshikurosawa/python-django-rest.git
$ cd app
```

Create a virtual environment to install dependencies in and activate it:

```sh
$ virtualenv2 --no-site-packages env
$ source env/bin/activate
```

Then install the dependencies:

```sh
(env)$ pip install -r requirements.txt
```
Note the `(env)` in front of the prompt. This indicates that this terminal
session operates in a virtual environment set up by `virtualenv2`.


## Docker Compose

The application can be lunched with Docker compose run this command to build the image and run
```sh
docker build .
docker-compose build
docker-compose up
```
application, run on this url `http://127.0.0.1:8000`.

### Django Admin

The application use Django Admin management use this command to create new superuser
```sh
docker-compose run app sh -c "python manage.py makemigrations core"
docker-compose run app sh -c "python manage.py createsuperuser"
```

## Tests

The application is TDD Base so to run the tests, use this command:
```sh
docker-compose run app sh -c "python manage.py test && flake8"
```