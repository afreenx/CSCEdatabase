


# CSCE310CRUD Real estate Application web application using Python with SQL Alchemy ,Flask 
and postgres SQL 
EPIC : Story: Customer and Real Estate Agent Management
As an admin (real estate agent), I want to be able to manage customer and real estate agent 
information, so that I can effectively handle property sales.
Down load Readme.pdf
[Readme.pdf](https://github.com/afreenx/CSCE310CRUD/files/12022334/Readme.pdf)


git clone https://github.com/afreenx/CSCE310CRUD

sudo -u postgres psql
postgres=# \password postgres
Enter new password: Supergmat123#

postgres=# \q


CREATE DATABASE estate WITH OWNER = postgres ENCODING = 'UTF8' CONNECTION LIMIT = -1;
\c estate


Invoke conda terminal

conda env create -f environment-mywebapp.yml
conda activate mywebapp

enter python shell by typing python  ---- This will create all tables in estate database from app.py file

from app import db

<hit enter>

db.create_all()

<hit enter>

  exit()


to run application

change to crud directory

flask run


