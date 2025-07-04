
# python-generators-0x00


## Overview

This project demonstrates advanced usage of Python generators for efficient data processing, focusing on real-world scenarios such as streaming large datasets from an SQL database. The codebase is designed to be modular, maintainable, and extensible, using best practices in Python systems architecture.

---

## Features

- **Database Initialization**: Automates setup of a MySQL database (`ALX_prodev`) and a `user_data` table with a clear schema.
- **CSV Data Seeding**: Seeds the database from a `user_data.csv` file, ensuring idempotency and integrity.
- **Generator Patterns**: Lays the groundwork for streaming database rows using Python generators, enabling memory-efficient data processing.
- **Extensible Design**: Functions are modular, type-annotated, and ready for extension with error handling, logging, and configuration.

---

## Learning Objectives

- Master Python generator functions for iterative, lazy data processing.
- Handle large datasets efficiently using batch processing and streaming.
- Integrate Python with SQL databases for robust data management.
- Write clean, reusable, and maintainable backend code.

---

## Project Structure

```
python-generators-0x00/
│
├── seed.py        # Database setup and seeding logic
├── 0-main.py      # Entry point for initializing and testing seed functionality
├── user_data.csv  # Sample data for seeding the database
└── README.md      # This documentation
```

---

## Usage

1. **Install Requirements**

   - Python 3.x
   - MySQL server (ensure it is running)
   - `mysql-connector-python` library

   ```bash
   pip install mysql-connector-python
   ```

2. **Configure Database Access**

   - By default, database connection uses:
     - host: `localhost`
     - user: `root`
     - password: `''` (empty)
   - Change these parameters in `seed.py` if your setup differs.

3. **Seed the Database**

   Run the main script to initialize the database and seed data:

   ```bash
   ./0-main.py
   ```

   **Expected Output:**
   ```
   connection successful
   Table user_data created successfully
   Database ALX_prodev is present 
   [(user_id, name, email, age), ...]
   ```

---

## Key Functions

- `connect_db()`: Connects to MySQL server (no DB selected).
- `create_database(connection)`: Creates `ALX_prodev` database if absent.
- `connect_to_prodev()`: Connects to the `ALX_prodev` database.
- `create_table(connection)`: Creates `user_data` table if it doesn't exist.
- `insert_data(connection, csv_path)`: Seeds table from CSV, avoiding duplicates.

---

##  Notes

- **Type Hints**: All functions are type-annotated for clarity.
- **Idempotency**: Seeding is safe to rerun; no duplicate users.
- **Extensibility**: Codebase is structured for easy extension—add logging, configuration, or error handling as needed.

## License

This project is part of the ALX Backend Python curriculum.
