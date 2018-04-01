---
title: 
category: Getting Started
chapter: 2
order: 1
---


Before installing Archery, you need to make sure you have Python and `pip`
– the Python package manager – up and running. You can verify if you're already
good to go with the following commands:

``` bash
python --version
# Python 2.7.13
pip --version
# pip 9.0.1



# Now clone Archery tool from github

git clone https://github.com/archerysec/archerysec.git


# Move to directory archerysec


cd /archerysec


# Install requirements

pip install -r requirements.txt


# Load static files

python manage.py collectstatic


# Makemigrations of all networkscanners app models

python manage.py makemigrations networkscanners

# Makemigrations of all webscanners app models

python manage.py makemigrations webscanners


# Makemigrations of all projects app models

python manage.py makemigrations projects


# Migrate all data

python manage.py migrate


# Now you need to create application Credentials

python manage.py createsuperuser


# Let's run the application

python manage.py runserver
```

