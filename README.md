# dmd
Django with MySQL on Docker

## Setup

You need to build a Docker image for Django:

    $ docker-compose build web

And you need to creat a database. First start the MySQL container:

    $ docker-compose up -d db

Then run mysql commands in the container:

    $ docker-compose exec db bash
    # mysql --user=root --password=password
    ....
    mysql> create database db_django;
    Query OK, 1 row affected (0.00 sec)
    mysql> exit
    Bye
    # exit

Now you need to uodate tablse in this database. Run Django migration:

    $ docker-compose run web python manage.py migrate

Now you can start the Django container. Run:

    $ docker-compose up -d

The site should be running on http://localhost:8989
