# PayPulse -- Digital Payment Failure and Refund Analytics System

## Project Overview

PayPulse is a MySQL database management system project designed to
organise digital payment transaction and refund information. It stores
details about customers, merchants, payment gateways, payment methods,
transaction statuses, transactions, refunds, and transaction status
history.

The database supports SQL-based analysis of payment outcomes and refund
activity.

## Objectives

-   Store payment and refund information in a structured relational
    database.
-   Track successful, failed, pending, processing, and cancelled
    transactions.
-   Maintain relationships between customers, merchants, gateways,
    payment methods, and transactions.
-   Analyse transaction and refund information using SQL queries.
-   Use indexes, views, and stored procedures to support reusable
    database operations.
-   Maintain a history of transaction status changes.

## Technologies Used

-   **Database:** MySQL Server 8.0
-   **Database tool:** MySQL Workbench
-   **ER diagram tool:** ERDPlus
-   **Language:** SQL (MySQL syntax)

## Database Schema

The `PAYPULSE` database contains the following eight tables:

  -----------------------------------------------------------------------
  Table                               Purpose
  ----------------------------------- -----------------------------------
  `CUSTOMERS`                         Stores customer details.

  `MERCHANTS`                         Stores merchant and business
                                      details.

  `PAYMENT_GATEWAYS`                  Stores payment gateway information.

  `PAYMENT_METHODS`                   Stores supported payment methods.

  `TRANSACTION_STATUSES`              Stores transaction status values.

  `TRANSACTIONS`                      Stores payment transaction records
                                      and references the related master
                                      tables.

  `REFUNDS`                           Stores refund references, amounts,
                                      dates, and refund statuses.

  `TRANSACTION_STATUS_HISTORY`        Stores transaction status history,
                                      including old and new status IDs.
  -----------------------------------------------------------------------

Primary keys identify records, and foreign keys connect related tables.
The schema also uses unique constraints and check constraints for data
integrity.

## Database Features

### Sample Data

The project uses sample records for customers, merchants, payment
gateways, payment methods, transaction statuses, transactions, refunds,
and status history.

### Indexes

The project defines these indexes:

-   `IDX_TRANSACTIONS_STATUS_TIME`
-   `IDX_TRANSACTIONS_MERCHANT_TIME`
-   `IDX_REFUNDS_TRANSACTION_STATUS`

### Views

-   `VW_FAILED_TRANSACTIONS` -- displays failed transactions with
    related customer, merchant, gateway, and payment-method details.
-   `VW_REFUND_ANALYTICS` -- combines refund, transaction, customer, and
    merchant information.
-   `VW_MERCHANT_PAYMENT_SUMMARY` -- summarises transaction counts,
    success/failure counts, and transaction amounts by merchant.

### Stored Procedures

-   `SP_GET_TRANSACTIONS_BY_STATUS` -- retrieves transactions for a
    supplied status name.
-   `SP_CUSTOMER_TRANSACTION_SUMMARY` -- returns a transaction summary
    for a supplied customer ID.
-   `SP_MERCHANT_TRANSACTION_SUMMARY` -- returns a transaction summary
    for a supplied merchant ID.

### SQL Query Bank

The project work includes 21 numbered SQL queries organised into three
levels and an additional query set:

-   Level 1: Q1--Q4 -- basic retrieval and filtering.
-   Level 2: Q5--Q8 -- grouping, aggregate functions, and subqueries.
-   Level 3: Q9--Q11 -- more advanced grouping, filtering, and joins.
-   Additional queries: Q12--Q21 -- further transaction and customer
    analysis.

## Setup and Execution

1.  Install MySQL Server 8.0 and MySQL Workbench.
2.  Open the project SQL script in MySQL Workbench.
3.  Execute the database and table creation statements.
4.  Insert the sample data.
5.  Create the indexes, views, and stored procedures.
6.  Execute the query bank to view the analysis results.
7.  Run the demo `SELECT` statements and stored procedure `CALL`
    statements to test the database objects.

> **Note:** Run the script in the order in which its sections are
> arranged. If you are rerunning a script against an existing database,
> check its database-creation and insert statements first to avoid
> duplicate data or unintentionally dropping existing objects.

## Example Commands

``` sql
USE PAYPULSE;

SELECT * FROM TRANSACTIONS;

SELECT * FROM VW_FAILED_TRANSACTIONS;

SELECT * FROM VW_REFUND_ANALYTICS;

SELECT * FROM VW_MERCHANT_PAYMENT_SUMMARY;

CALL SP_GET_TRANSACTIONS_BY_STATUS('FAILED');

CALL SP_CUSTOMER_TRANSACTION_SUMMARY(1);

CALL SP_MERCHANT_TRANSACTION_SUMMARY(1);
```

## Project Structure

A simple GitHub repository structure can be:

``` text
PAYPULSE/
├── README.md
├── PAYPULSE.sql
└── ER_Diagram.png
```

Add the SQL script that contains your final, complete implementation.
Add your ER diagram image only if you want it displayed in the
repository.

## Author

**THOTAKURA DURGA SRI**

B.Tech Project -- GITAM
