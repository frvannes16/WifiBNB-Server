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


## The meat and potatoes of Django

There are 3 main files involved in Django:
- `urls.py` <- Where you define the URL routes. Like /hello-world
- `views.py` <- Where you define the functions handlers to process HTTP requests and responses. `urls.py` will reference these functions.
- `models.py` <- Where you define the DB schema.

Typically, you can build an entire web app using these three files. The `urls.py` file will have valid URLs defined, that will use functions registered in `views.py` to handle requests. Functions in `views.py` will use objects defined in `models.py` to query the Database by using Django's ORM.


## Django ORM

The Django ORM is our portal to interacting with objects in the datase.
Here is an example of how it works.


In `models.py`, we define a database model:

```
from django.db import models

class Book(models.Model):
    name = models.CharField(max_length=500)
    author = models.CharField(max_length=200)
    release_date = models.DateTimeField()
    is_good_book = models.BooleanField(default=False)

```

After running `python manage.py makemigrations` and `python manage.py migrate` to register the `Book` model with the Database, we can then use `Book.objects` to access Books stored in the datbase. See the examples below:

1. Create Books in the database

```
moby_dick = Book.objects.create(name="Moby Dick", author='Herman Melville', release_date='1924-10-29', is_good_book=False)
```

2. Retrieve Books from the database

```
moby_dick = Books.objects.get(name="Moby Dick")
```

3. Update books from the database

```
moby_dick = Books.objects.get(name="Moby Dick")
moby_dick.author = "Me. I wrote it!"
moby_dick.save()
```

4. Delete books from the database

```
moby_dick = Book.objects.get(name="Moby Dick")
moby_dick.delete()
```




