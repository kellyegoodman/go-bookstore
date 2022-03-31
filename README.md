# go-bookstore
:books: Simple MySQL API written in Go. The API handles http requests to create, update, and delete book entries in a bookstore database . This code follows a tutorial given by Akhil Sharma https://www.youtube.com/watch?v=1E_YycpCsXw

## Prerequisites
1. Go installed
2. MySQL installed

## Build and run
1. Modify line 13 of pkg/config/app.go to have your MySQL credentials.As is, the app.go file has the MySQL username and password hard-coded as "root" and "root". These credentials need to be updated to one of your local MySQL users.
2. Create a bookstore database in MySQL
    
    ```
    mysql -u <user> -p
    mysql> CREATE DATABASE bookstore;
    mysql> quit
    ```
    
3. Build and start the server with the following commands:

    ```
    cd <cloned_repo>/cmd/src
    go build
    go run main.go
    ```
    
4. In a service like Postman, create 5 new requests
    | Request Name | Method | URL |
    | --- | --- | --- |
    | GET ALL | GET | localhost:9010/book/ |
    | GET BY ID | GET | localhost:9010/book/{id} |
    | CREATE | POST | localhost:9010/book/ |
    | UPDATE | PUT | localhost:9010/book/{id} |
    | DELETE | DELETE | localhost:9010/book/{id} |
    
5. Experiment with running the various requests to create, update, and delete books from the bookstore database. The entries will now persist between restarts of the go server.
You can also view the contents of the database by connecting to mysql via the terminal / command line.
![alt text](example_mysql_books_db.png)
