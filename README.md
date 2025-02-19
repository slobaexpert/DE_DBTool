# DE_DBTool - Secure & Versatile Database Utility

## Overview
DE_DBTool is a powerful **cross-platform database management tool** designed to handle **SQL and NoSQL databases** efficiently. This tool enables seamless **database interactions**, **secure authentication**, and **data extraction** in a simple and automated manner.

With support for **SQL Server, Oracle, MySQL, PostgreSQL, MongoDB, and Cassandra**, DE_DBTool provides **flexibility for future database versions** while ensuring **encrypted credential handling** and **secure database connectivity**.

## Features
- ✅ **Cross-Platform Support** – Runs on **Windows and Linux** with `.zip` and `.tar` packaging.
- ✅ **Multi-Database Compatibility** – Supports **SQL Server, Oracle, MySQL, PostgreSQL, MongoDB, Cassandra**.
- ✅ **Encrypted & Secure Authentication** – Works with **plain or encrypted passwords**, and can integrate with **vault-based authentication**.
- ✅ **Comprehensive SQL Operations** – Supports **SELECT, INSERT, UPDATE, DELETE, and UNLOAD** operations.
- ✅ **Configurable Connection Settings** – Uses an easily customizable **`db_config.json`** for database connection management.
- ✅ **Efficient Data Unloading** – Extracts data into **CSV, TXT, or custom-delimited formats**.
- ✅ **Command-Line Friendly** – Provides a **help command (`--help`)** for ease of use.
- ✅ **Future-Proof** – Designed to **support future database versions and enhancements**.

## Installation
### Windows
1. Download the latest `db_tool.zip` from the **Releases** section.
2. Extract the files and navigate to the directory.
3. Run the tool using:
   ```sh
   DE_DBTool.exe -c db_config.json -a select -sql "SELECT * FROM users;" -o output.txt
   ```

### Linux
1. Download the latest `db_tool.tar` from the **Releases** section.
2. Extract the files:
   ```sh
   tar -xvf db_tool.tar
   ```
3. Grant execution permissions:
   ```sh
   chmod +x DE_DBTool
   ```
4. Run the tool:
   ```sh
   ./DE_DBTool -c db_config.json -a select -sql "SELECT * FROM users;" -o output.txt
   ```

## Configuration
The tool requires a **JSON-based configuration file (`db_config.json`)** to establish connections:

```json
{
    "DB_TYPE": "mysql",
    "DB_HOST": "localhost",
    "DB_PORT": "3306",
    "DB_NAME": "mydatabase",
    "DB_USER": "admin",
    "DB_PASS": "password123",
    "ENCRYPTED": "false"
}
```

For **encrypted passwords**, set `"ENCRYPTED": "true"` and specify an encryption key.

## Usage
### **Basic Command Structure**
```sh
DE_DBTool -c <config_file> -a <action> -sql "<SQL_Query>" -o <output_file> [-d <delimiter>] [-header]
```

### **Examples**
#### **1. Execute a Query (SELECT)**
```sh
DE_DBTool -c db_config.json -a select -sql "SELECT * FROM employees;" -o employees.csv -d ","
```

#### **2. Insert a Record**
```sh
DE_DBTool -c db_config.json -a insert -sql "INSERT INTO employees (id, name, department) VALUES (101, 'John Doe', 'HR');"
```

#### **3. Unload Data**
```sh
DE_DBTool -c db_config.json -a unload -sql "SELECT * FROM sales;" -o sales_report.csv -header
```

#### **4. View Help Options**
```sh
DE_DBTool --help
```

## Packaging & Deployment
The tool is **distributed as a `.tar` (Linux) and `.zip` (Windows)** for easy deployment.

#### **Package the Tool**
- **Windows:**  
  ```sh
  zip -r db_tool.zip db_config.json DE_DBTool.exe
  ```
- **Linux:**  
  ```sh
  tar -cvf db_tool.tar db_config.json DE_DBTool
  ```

## Contributing
We welcome **contributions** to enhance DE_DBTool!  
To contribute:
1. **Fork** the repository.
2. Create a **feature branch** (`git checkout -b feature-xyz`).
3. Commit your changes (`git commit -m "Added new feature"`).
4. **Push** to your branch and create a **Pull Request**.

## License
Released under the **MIT License**.

