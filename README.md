ATM Simulator System



Project Overview
This is an ATM Simulator System project designed to simulate the functionalities of an ATM, including:

Frontend: Developed using HTML, CSS, and JavaScript for the user interface.


Backend: Implemented in Java, with database connectivity to simulate transactions and account management.


The system allows users to:



Log in with an account.

Check balance.

Withdraw money.

Deposit money.


Table of Contents
Technologies Used
Features
Frontend
Backend
Database Connectivity
How to Run the Project
Folder Structure
Contributors
Technologies Used
Frontend:


HTML

CSS

JavaScript

Backend:



Java (Spring Boot or Servlet-based)


Database:

MySQL / PostgreSQL / SQLite (depending on your choice)
Features



Login Authentication: Users can log in with a username and pin.

Balance Enquiry: View account balance.

Deposit Funds: Option to deposit money into the account.

Withdraw Funds: Option to withdraw money from the account.

Transaction History: View transaction details (withdrawal and deposit logs).


Frontend
The frontend is developed using HTML, CSS, and JavaScript. It provides a simple, interactive interface for users to interact with the ATM system.

Login Page: Allows users to input their account details (username and pin).

ATM Dashboard: Displays the options to check balance, deposit money, withdraw money, etc.


Backend
The backend is built using Java with a choice of frameworks (Spring Boot / Servlets). It handles the business logic of the ATM system, such as validating login details, performing transactions, and interacting with the database.



API Endpoints:

POST /login: Validate user credentials.

GET /balance: Retrieve the account balance.

POST /withdraw: Process withdrawal requests.

POST /deposit: Process deposit requests.

GET /transaction-history: Fetch transaction logs.



Database Connectivity
The database is used to store user account information, including:

User Table: Stores username, pin, and balance.


Transaction Table: Logs all transactions (deposits/withdrawals) performed by the user.


We have used MySQL (or any other database you choose) for this project.


Example SQL queries:


sql



CREATE TABLE Users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    pin VARCHAR(10) NOT NULL,
    balance DECIMAL(10, 2) DEFAULT 0
);




CREATE TABLE Transactions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    type ENUM('deposit', 'withdraw') NOT NULL,
    amount DECIMAL(10, 2),
    date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY(user_id) REFERENCES Users(id)
);



How to Run the Project

Prerequisites

Frontend: HTML, CSS, JavaScript (can be opened in any modern web browser)

Backend: Java (JDK 11 or above), Maven (for dependencies and building)

Database: MySQL (or your preferred database)


Steps to Run:


Clone the repository:


bash


git clone https://github.com/your-username/ATM-Simulator-System.git

cd ATM-Simulator-System

Set up the database:


Create a MySQL database and import the SQL scripts for user and transaction tables.

Modify the database connection details in the application.properties (or equivalent config file in your backend).
Backend Setup (Java):


If using Maven, build the Java backend:

bash


mvn clean install

Run the backend server:
bash

mvn spring-boot:run
Or, if using a servlet, deploy it to your servlet container (Tomcat).
Frontend Setup (HTML/CSS/JS):



Open the index.html file in any web browser.


The frontend will connect to the backend server for all transactions.
Folder Structure


bash




ATM-Simulator-System/
│
├── frontend/                      # Frontend files (HTML, CSS, JavaScript)
│   ├── index.html
│   ├── style.css
│   ├── app.js
│
├── backend/                       # Backend files (Java)
│   ├── src/
│   ├── application.properties     # Database and app configurations
│   ├── pom.xml                    # Maven dependencies (if using Maven)
│   ├── TransactionController.java # Backend logic for transactions
│   ├── UserService.java           # Service for handling user operations
│
├── README.md                      # Project documentation
├── .gitignore                     # Git ignore file





That's it! You're all set. 🚀
Let me know if you need any further help!
