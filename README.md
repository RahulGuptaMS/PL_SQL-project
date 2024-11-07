# **Hotel Management System**

This project is a Hotel Management System application built using Python with the Tkinter GUI toolkit and MySQL database for data storage. It provides functionalities for hotel check-in, check-out, guest data display, and history management, making it useful for managing a small hotel.

## **Features**

- **Room Availability Check**: View available rooms in the hotel.
- **Guest Check-In**: Check in guests by entering their details and assigning an available room.
- **Guest Check-Out**: Check out guests and update the database accordingly.
- **Guest List**: Display all current guests who have checked in.
- **Guest History**: View a record of all guests who have checked out.

## **Database**

The project uses MySQL as the database to store guest data. Follow these steps to set up the database.

### **Database Setup**

1. **Create the Database**: Run the following SQL command to create the database.

    ```sql
    CREATE DATABASE hotel;
    USE hotel;
    ```

2. **Create Tables**: Define the tables required for the application.

    - **guests**: Stores information about current guests.
    - **checked_out_guests**: Stores information about guests who have checked out.
    
    ```sql
    CREATE TABLE guests (
        id INT AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(100),
        phone VARCHAR(15),
        gender VARCHAR(10),
        email VARCHAR(100),
        days INT,
        room_number INT,
        total_cost INT
    );

    CREATE TABLE checked_out_guests (
        id INT AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(100),
        phone VARCHAR(15),
        gender VARCHAR(10),
        email VARCHAR(100),
        days INT,
        room_number INT,
        total_cost INT,
        checkout_date DATETIME DEFAULT CURRENT_TIMESTAMP
    );
    ```

3. **View Guest Data**: Use the following query to view all guests.

    ```sql
    SELECT * FROM guests;
    ```

## **Prerequisites**

- Python 3.x
- MySQL server
- `pymysql` library for MySQL connectivity:
  
    ```bash
    pip install pymysql
    ```

## **Getting Started**

1. **Clone the Repository**: [https://github.com/RahulGuptaMS/PL_SQL-project/](https://github.com/RahulGuptaMS/PL_SQL-project/)
   
    ```bash
    git clone <your-repository-url>
    ```

2. **Configure Database Connection**: Update the MySQL credentials in the script (username, password) to match your MySQL server setup.

3. **Run the Application**: Run the script using Python.

    ```bash
    python hotel_management.py
    ```

## **Usage**

- **Fetch Available Room Data**: View which rooms are currently available.
- **Check In a Guest**: Fill in guest details, including name, phone number, gender, email, and duration of stay. The system assigns a room and calculates the total cost.
- **Check Out a Guest**: Select a guest to check out, freeing up the room for future use.
- **Show All Guest List**: View a list of all currently checked-in guests.
- **Show Guest History**: Display a history of all checked-out guests
