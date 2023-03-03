# django-el

Set up virtual environment

`python3 -m venv venv`

activate it with

`source venv/bin/activate`

but in the fish shell, use

`source venv/bin/activate.fish`

for deactivating it, in any shell

`deactivate`

### Creating django project

run the following command

`django-admin startproject mysite`

### Creating apps

remember, a project can have many apps, and the same app can be in different projects

Django apps are “pluggable”: You can use an app in multiple projects, and you can distribute apps, 
because they don’t have to be tied to a given Django installation.

to create an app, go inside a project directory and run:

`python manage.py startapp polls`

to run the server:

`python manage.py runserver`

run migrations to make out of the box apps in settings.py INSTALLED_APPS run without errors

`python manage.py migrate`

when installing an app into settings.py or making model changes, 
if you would like to store the changes as a migration:

`python manage.py makemigrations polls`

There’s a command that will run the migrations for you and manage your database schema automatically, 
which is called `migrate`

To check what SQL code a migration will run:
`python manage.py sqlmigrate polls 0001`

If you’re interested, you can also run `python manage.py check`
this checks for any problems in your project without making migrations or touching the database.

Now, run `python manage.py migrate` again to create those model tables in your database

remember the three-step guide to making model changes:

* Change your models (in models.py).
* Run python manage.py makemigrations to create migrations for those changes
* Run python manage.py migrate to apply those changes to the database.

## Playing with the API

To invoke the Python shell, use this command:

`python manage.py shell`

We’re using this instead of simply typing “python”, 
because manage.py sets the DJANGO_SETTINGS_MODULE environment variable, 
which gives Django the Python import path to your mysite/settings.py file.

