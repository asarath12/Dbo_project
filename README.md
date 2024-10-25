# Database Manager Application
This project is a Python-based database management application that allows users to interact with a MySQL database through a console interface. It supports CRUD (Create, Read, Update, Delete) operations for multiple tables within a schema. The application provides a menu-driven interface to manage records across various tables and is designed with error handling for an enhanced user experience.

## Table of Contents
- [Features](#features)
- [Supported Tables](#supported-tables)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Error Handling](#error-handling)
- [Code Structure](#code-structure)
- [Future Enhancements](#future-enhancements)

## Features
- **Create Record**: Allows inserting new records into specified tables, ensuring the necessary constraints are met.
- **Read Record**: Retrieves and displays all records from the selected table.
- **Update Record**: Modifies existing records in the database using primary key(s) for identification.
- **Delete Record**: Deletes specific records from a table based on primary key(s).
- **Error Handling**: Includes error handling for invalid options, database connection issues, and constraint violations.

## Supported Tables

The application supports the following tables:

1.  accident
1.  address
1.  camera
1.  phonenumber
1.  road
1.  roadcamera
1.  user
1.  vehicle
1.  vehicleviolation
1.  violation

These tables are managed using primary keys, and relationships between them are enforced by the application logic.

## Setup Instructions

### Prerequisites

- Python 3.x installed on your system.
- MySQL server running with a valid database schema.
- MySQL Connector for Python (mysql-connector-python package).

### Installation

1. Clone or download this repository to your local machine.

1. Install the MySQL connector package if not already installed:
   
```bash
pip install mysql-connector-python
```

3. Update the database connection credentials in the code:

```bash
db = DatabaseManager(host="localhost", user="root", password="YourPassword", database="YourDatabase")
```

Ensure the database schema is set up with the required tables and relationships.

## Usage

1. **Run the application**:

```bash
python your_script_name.py
```

2. **Menu Options**:

- The application will display a menu with five options:

  - Create a new record
  - Read a record
  - Update a record
  - Delete a record
  - Exit

- Choose an option by entering the corresponding number (1-5).

3. **CRUD Operations**:

- Create: Select a table, then provide the required fields. The application checks for constraints like foreign key relationships before insertion.
- Read: Select a table to view all its records.
- Update: Choose the table, specify the primary key(s), and update the desired column's value.
- Delete: Choose the table and provide the primary key(s) to delete the record.

4. **Exit**:

- To exit the application, select option 5. The application will close the database connection.

## Error Handling

- **Database Connection**: If the application fails to connect to the MySQL database, it displays an error message and exits gracefully.
- **Invalid Menu Options**: If an invalid menu option is selected, the application prompts the user to try again.
- **Table and Column Selection**:
  - The application validates the user's choice when selecting tables and columns.
  - If a non-existent or invalid option is chosen, the application provides feedback and asks the user to make a valid selection.
- **Constraint Violations**: The application enforces foreign key constraints. If a user tries to insert a record with a non-existent ID in a referenced table, it displays an error message.

## Code Structure

### DatabaseManager Class

This class is responsible for handling all database interactions and operations. It contains the following methods:

- init: Establishes a connection to the MySQL database.
- create_record: Inserts new records into the specified table.
- read_record: Retrieves and displays all records from the selected table.
- get_columns: Fetches the column names for the selected table.
- update_record: Updates a record based on the specified primary key and column.
- delete_record: Deletes a record using the primary key(s) for identification.
- close_connection: Closes the database connection when the application exits.

### main Function

This function manages the application flow:

- Displays the main menu.
- Takes user input for various operations.
- Calls the appropriate methods from the DatabaseManager class based on the user’s choice.

### Future Enhancements

- **User Authentication**: Add user login functionality to restrict access based on roles.
- **Enhanced Validation**: Implement additional validation checks (e.g., format of inputs like phone numbers or dates).
- **Search Functionality**: Allow users to search records based on specific column values (e.g., search by license plate).
- **Logging**: Implement logging for auditing user actions and debugging purposes.
- **GUI Interface**: Extend the application to include a graphical user interface for better user experience.


