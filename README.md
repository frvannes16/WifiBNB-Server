# WifiBNB Server

This Django project is the server portion of our Hack It, Ship It hackathon submission. This server stores WIFI SSIDs, locations, and credentials for users of the platform to rent from.

## Getting Started

First, download and install python 3.8, pip, and venv:

Installing python: https://www.python.org/downloads/
Installing pip and venv: https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/

Create a new python virtual environment for this project.
`mkvirtualenv --python=python3 wifibnb`

Install the project dependencies:
`pip install -r requirements.txt`

And you are good to go!

## Project commands

`python manage.py runserver` - Runs the server locally.

`python manage.py makemigrations` - converts the python-defined DB schema into python migration files that can be run on the DB.

`python manage.py migrate` - runs the migration files on the DB, applying our django defined schema to the database.

`python manage.pt test` - runs any tests that we have defined.

## Django Admin

After running `python manage.py runserver` you can visit the project admin dashboard by going to `localhost:8000/admin`. Here, we can register our database models for manipulation and creation via this interface.
