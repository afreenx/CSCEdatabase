


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

CREATE TABLE customer (
    customer_id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    contact_details VARCHAR(100),
    account_balance NUMERIC(10, 2));

CREATE TABLE real_estate_agent (
    agent_id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    contact_details VARCHAR(100));
    
CREATE TABLE real_estate (
    property_id SERIAL PRIMARY KEY,
    title VARCHAR(100),
    location VARCHAR(100),
    price NUMERIC(10, 2),
    listing_date DATE,
    sell_date DATE,
    customer_id INTEGER,
    FOREIGN KEY (customer_id) REFERENCES customer (customer_id) ,agent_id INTEGER);




Invoke conda terminal

conda env create -f environment-mywebapp.yml

conda activate mywebapp

# skip if you create manually
enter python shell by typing python  ---- This will create all tables in estate database from app.py file

from app import db

<hit enter>

db.create_all()

<hit enter>

  exit()

note in case trouble creating table using apps create manually as in table script file.

to run application
## skip end
change to crud directory

flask run

URLS
http://127.0.0.1:5000 ( main page)

http://127.0.0.1:5000/realestates

http://127.0.0.1:5000/customers

http://127.0.0.1:5000/agents


