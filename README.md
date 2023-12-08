# INFO 210 – Database Management Systems

## Assignment – Milestone 4

Bonus Points: Database Access from a Programming Language

> For any inquiries or issues, please feel free to contact me at `320220940211@lzu.edu.cn`.
> Thank you for the patient correction and guidance throughout this assignment and the entire INFO-210 Course!

## Introduction

This is a simple command-line tool written in Python for querying a PostgreSQL database using Psycopg2. It provides a basic interface for users to run SQL queries, retrieve data from a specified table, and exit the program.

In order to facilitate group work and optimize the program experience, we have deployed the PostgreSQL database to my Linux server, and this program defaults to connecting to this database through the network (`47.236.6.228:5432`). If you want to connect to a local database, please modify the parameters in the `def main()`function of the `main.py` file to:

```python
def main():
    connection = connect_to_database("your_user", "your_password", "localhost", "5432", "your_database")
```

## Prerequisites

Before running the program, make sure you have the following installed:

- Python 3.8+
- Psycopg2 library:

```bash
pip install psycopg2
pip install psycopg2-binary
```

Of course, we have also attached the development environment of the project to this folder (./envs), and you can activate this environment to run the program:

```bash
conda activate ./envs/
python main.py
```

## Features

### `connect_to_database(usr, pw, hst, pt, db)`

Connects to a PostgreSQL database using the provided credentials.

- **Parameters:**

  - `usr`: Database username.
  - `pw`: Database password.
  - `hst`: Database host address.
  - `pt`: Database port.
  - `db`: Database name.

- **Returns:**

  - PostgreSQL connection object.

---

### `truncate_string(s, max_length)`

Truncates a string if it exceeds a specified maximum length.

- **Parameters:**

  - `s`: The input string.
  - `max_length`: The maximum length before truncation.

- **Returns:**

  - The truncated string.

---

### `execute_query(connection, query, max_cell_length=30)`

Executes a SQL query and formats the result for display.

- **Parameters:**

  - `connection`: PostgreSQL database connection object.
  - `query`: SQL query to be executed.
  - `max_cell_length`: Maximum length for each cell in the output table (default is 30).

- **Prints:**

  - The formatted result of the query or an error message if execution fails.

---

### `main()`

The main function that runs the command-line interface.

- **Behavior:**

  - Connects to a PostgreSQL database.
  - Presents a menu for the user to choose options:
    - `Run a SQL query`: Accepts user input for a custom SQL query and executes it.
    - `Query all data in a table`: Accepts user input for a table name and queries all data from the specified table.
    - `Exit`: Exits the program.

- **Parameters:**

  - No parameters.

- **Prints:**

  - Information and query results based on user choices.

---

**Note:** Replace placeholder values in the `connect_to_database` function with actual database credentials. Adjust formatting options in the `execute_query` function for better output as needed.