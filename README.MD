# Go MySQL Tutorial
This is a simple Go program that demonstrates how to connect to a MySQL database and retrieve data from a table. It uses the database/sql package to interact with the database and the go-sql-driver/mysql package as the MySQL driver.

## Prerequisites
Before running this program, make sure you have the following:

Go programming language installed on your system.

MySQL server installed and running.

The go-sql-driver/mysql package installed. You can install it by running the following command:

```go
go mod init "github.com/yourUserName/yourRepository"
go mod tidy
```

## Usage
Modify the database connection string in the sql.Open function call to match your MySQL server configuration. 
The format is as follows:

```
username:password@tcp(hostname:port)/databasename
```

Replace username and password with your MySQL credentials, hostname and port with the appropriate values, and databasename with the name of the database you want to connect to.

Compile and run the program using the following command:

```
go run main.go
```

The program will establish a connection to the MySQL database, execute a query to select all names from the users table, and print the retrieved names to the console.

You can uncomment the code section related to inserting data into the users table if you want to experiment with inserting data. Make sure to comment out the query execution section before running the insertion code.

```
// insert, err := db.Query("INSERT INTO users VALUES('JOHN')")

// if err != nil {
// 	panic(err.Error())
// }

// defer insert.Close()

// fmt.Println("Successfully inserted into user tables")
```

Once you're done, terminate the program. The database connection will be closed automatically using the defer statement.

## Notes
- This code is intended as a basic example and should be adapted for production use. Proper error handling, input validation, and security measures should be implemented for a real-world application.
- Ensure that you have the necessary permissions and the correct database schema to run the queries successfully.
- Remember to protect sensitive information such as database credentials and connection strings. Avoid hardcoding them in the source code, and consider using environment variables or configuration files instead.