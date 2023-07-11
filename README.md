# CSCE310CRUD  Real estate Application web application using Python with SQL Alchemy ,Flask and postgres SQL 
EPIC : Story: Customer and Real Estate Agent Management

As an admin (real estate agent), I want to be able to manage customer and real estate agent information, so that I can effectively handle property sales.

Project overview steps
postgres=#

•	CREATE DATABASE estate WITH OWNER = postgres ENCODING = 'UTF8' CONNECTION LIMIT = -1;
•	\c estate
crud Structure
crud/
├── app.py
├── templates/
│   ├── customers.html
│   ├── create_customer.html
│   ├── agents.html
│   ├── create_agent.html
│   ├── realestates.html│   
└── create_real_estate.html
└── ...



TABLES : CREATE TABLE customer (
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
    FOREIGN KEY (customer_id) REFERENCES customer (customer_id));

Note I need to alter and migrate
ALTER TABLE real_estate ADD COLUMN agent_id INTEGER;
ALTER TABLE real_estate ALTER COLUMN sell_date DROP NOT NULL;
ALTER TABLE real_estate ALTER COLUMN sell_date SET DEFAULT NULL;

we can simply create 
CREATE TABLE real_estate (
    property_id SERIAL PRIMARY KEY,
    title VARCHAR(100),
    location VARCHAR(100),
    price NUMERIC(10, 2),
    listing_date DATE,
    sell_date DATE,
    customer_id INTEGER,
    FOREIGN KEY (customer_id) REFERENCES customer (customer_id) ,agent_id INTEGER);

    CRUD Routes in app.py
    ==========================
    Customer CRUD:

Create: Provide a form for the agent to add a new customer to the database.
Read: Display a list of all customers, showing their details.
Update: Allow the agent to edit the details of a specific customer.
Delete: Provide an option to delete a customer from the database.
Real Estate Agent CRUD:

Create: Provide a form for the agent to add a new real estate agent to the database.
Read: Display a list of all real estate agents, showing their details.
Update: Allow the agent to edit the details of a specific real estate agent.
Delete: Provide an option to delete a real estate agent from the database.
Real Estate CRUD:

Create: Provide a form for the agent to add a new real estate property to the database.
Read: Display a list of all real estate properties, showing their details.
Update: Allow the agent to edit the details of a specific real estate property.
Delete: Provide an option to delete a real estate property from the database.
Defined routes and corresponding view functions in your app.py file. 

URLS
http://127.0.0.1:5000  ( main page)
http://127.0.0.1:5000/realestates
http://127.0.0.1:5000/customers
http://127.0.0.1:5000/agents

Install all packages mentioned in app.py import
cd crud

flask run
crud>flask run
 * Debug mode: off
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on http://127.0.0.1:5000
Press CTRL+C to quit
127.0.0.1 - - [11/Jul/2023 14:04:52] "GET /customers HTTP/1.1" 200 -
127.0.0.1 - - [11/Jul/2023 14:04:57] "GET / HTTP/1.1" 200 -






    

