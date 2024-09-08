Courier Service Management System
Overview :
This is a Java-based Courier Service Management System that allows users to manage parcels and customers. The system provides features such as adding, viewing, updating, and deleting parcels and customers.
Setup Instructions :
Database Setup
Create a MySQL database named courier_service.
Create the following tables:
Parcel: parcel_id (primary key), sender_name, sender_address, recipient_name, recipient_address, weight, distance
Customer: customer_id (primary key), customer_name, email, phone_number, customer_address
You can use the following SQL script to create the table: 
CREATE TABLE Parcel (
  parcel_id INT PRIMARY KEY,
  sender_name VARCHAR(255),
  sender_address VARCHAR(255),
  recipient_name VARCHAR(255),
  recipient_address VARCHAR(255),
  weight DOUBLE,
  distance DOUBLE
);

CREATE TABLE Customer (
  customer_id INT PRIMARY KEY,
  customer_name VARCHAR(255),
  email VARCHAR(255),
  phone_number VARCHAR(255),
  customer_address VARCHAR(255)
);

CREATE TABLE Delivery (
    delivery_id INT AUTO_INCREMENT PRIMARY KEY,
    parcel_id INT,
    customer_id INT,
    delivery_date DATE,
    delivery_status ENUM('Scheduled', 'In Transit', 'Delivered'),
    delivery_cost DOUBLE,
    FOREIGN KEY (parcel_id) REFERENCES Parcel(parcel_id) ON DELETE CASCADE,
    FOREIGN KEY (customer_id) REFERENCES Customer(customer_id) ON DELETE CASCADE
);

Java Setup
Install Java Development Kit (JDK) 8 or later.
Install an IDE such as Eclipse or IntelliJ IDEA.
Import the project into your IDE.
Database Connection
Update the CourierServiceApp.java file with your MySQL database credentials.
Replace root with your MySQL username and password with your MySQL password.
Usage Instructions

Run the Application
Run the CourierServiceApp.java file.
The application will prompt you to select an option:
Add Parcel
View Parcel
Update Parcel
Delete Parcel
Register Customer
View Customer
Update Customer
Add Parcel
Enter the sender's name, address, recipient's name, address, weight, and distance.
The parcel will be added to the database.
View Parcel
Enter the parcel ID.
The parcel details will be displayed.
Update Parcel
Enter the parcel ID and the updated details.
The parcel will be updated in the database.
Delete Parcel
Enter the parcel ID.
The parcel will be deleted from the database.
Register Customer
Enter the customer's name, email, phone number, and address.
The customer will be added to the database.
View Customer
Enter the customer ID.
The customer details will be displayed.
Update Customer
Enter the customer ID and the updated details.
The customer will be updated in the database.