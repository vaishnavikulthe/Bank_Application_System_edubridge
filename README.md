# Bank Application System (Edubridge)

This project is a Java-based banking application system that allows users to perform various banking operations. Below, you will find details on how to use this application.

## Features

### 1. Account Creation

- To create an account, users provide personal information. Once the account is
successfully created, users receive account details for future login.

### 2. Login

To log in to your account, use the following steps:
-  Users enter their registered Account number and pin to access their account.
Upon successful login, users gain access to their account dashboard and
available banking features.
- After login in :
  • Users can "Check Balance" to view their account's available funds and recent
transactions.
  • "Deposit Money" allows them to add Money.
  • For cash needs, "Withdraw Money" facilitates ATM cash withdrawals or
electronic transfers.
  • "Money Transfer" enables users to move funds between accounts, both within
their bank and to other recipients.
  • "Mini Statement" generates a summary of recent transactions, showing dates,
types, and amounts.
  • Users can "Update" account details like contact information pin, Name, DOB,
Address.
  • "Show Details" provides a comprehensive account overview transaction
history, balances, and account status, aiding in managing their finances
effectively

### 3. Mini Statement

- A mini statement for a banking application provides a concise overview of
recent account activity, including transfers, withdrawals, and debit transactions. It
displays transaction details such as date, description, amount, and running balance,
allowing account holders to quickly track their financial transactions and monitor
their account balance. 

### 4. Withdraw Money

- The withdrawmoney method you provided is a Java method designed to handle the
withdrawal of money from a bank account.
The user is prompted to enter the amount of money they want
to withdraw (money). The method checks whether the entered amount is greater than
zero and whether it is less than or equal to the account's current balance (retrieved from
the resultset). If the conditions are not met, appropriate error messages are displayed.

### 5. Deposit Money

-  the process of depositing
money into a user's account. It ensures that the deposit is valid, updates the account balance,
records the transaction, and provides the user with a confirmation message.
The depositmoney() method in a banking application is responsible for allowing a user to deposit
money into their bank account.

### 6. Show Details

- Displays comprehensive account information, including account type,
transaction history, and account status.

### 7. Update Account

- You can implement the update logic for Last Name, Date of Birth, Phone Number, Address, and
PIN within their respective case statements. Make sure to handle user input and database
operations properly, and replace the login logic with your actual authentication mechanism.

### 8. Transfer Money

- The transferMoney method in a banking application is designed to handle the process of
transferring money into a specific bank account. Facilitates secure and convenient fund transfers between accounts or to
other beneficiaries.

## Database Schema
The project uses a MySQL database with three tables: Account, After_updatedd, and ministatement. Here are the schemas for each table:
- Account Table :-
  CREATE TABLE account (
 -> fname VARCHAR(45) NOT NULL,
 -> lname VARCHAR(45) NOT NULL,
 -> dateStr VARCHAR(45) NOT NULL,
 -> phoneno BIGINT NOT NULL UNIQUE,
 -> adharno VARCHAR(45) NOT NULL UNIQUE,
 -> gender VARCHAR(45) NOT NULL,
 -> address VARCHAR(45),
 -> accno VARCHAR(45) NOT NULL PRIMARY KEY,
 -> pin2 VARCHAR(4),
 -> balance DOUBLE NOT NULL
 -> );


- After_updatedd Table :-
    CREATE TABLE after_updatedd (
 -> user VARCHAR(45) NULL,
 -> status TEXT NULL,
 -> fname VARCHAR(45) NULL,
 -> lname VARCHAR(45) NULL,
 -> dateStr VARCHAR(45) NULL,
 -> phoneno VARCHAR(10) NULL,
 -> address VARCHAR(45) NULL,
 -> pin2 VARCHAR(4) NULL
 -> );

- Creating Trigger :
  Mysql->DELIMITER //
->CREATE TRIGGER after_account_update
->AFTER UPDATE ON account FOR EACH ROW
->BEGIN
-> INSERT INTO after_updatedd(user,status,accno, fname, lname, dateStr, phoneno, address, pin2)VALUES
(current_user(),CONCAT('Updated by ',OLD.accno,' ',now()),OLD.fname, OLD.lname, OLD.dateStr,
OLD.phoneno, OLD.address,OLD.pin2 );
->END;
->//

- Ministatement :
  create table ministatement(accno varchar(12),
  date datetime,
  double withdraw,
  double credit,
  double credit);


## Usage

- A banking management project using Core Java, MySQL, and JDBC is used for:

1) Account Management: Creating, updating, and managing customer accounts.
2) Transaction Handling: Facilitating deposits, withdrawals, transfers, and generating transaction history.
3) Data Persistence: Storing and retrieving banking data securely in a MySQL database.
4) Security and Compliance: Ensuring the safety of sensitive financial information and compliance with banking regulations.

## Contact

- If you have any questions or suggestions, please feel free to contact vaishnavikulthe345@gmail.com.

