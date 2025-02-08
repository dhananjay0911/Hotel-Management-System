# Hotel-Management-System

This is a Java-based Hotel Reservation System that allows users to:
-Reserve a room
-View reservations
-Retrieve room numbers based on guest name
-Update reservation details
-Delete reservations

The project uses JDBC (Java Database Connectivity) to interact with a MySQL database.

#Features
-Simple console-based interface
-CRUD operations on reservations
-MySQL database integration

#Prerequisites

Before running the project, ensure you have the following installed:
1.Java Development Kit (JDK) 8+
  -Download from: Oracle JDK

2.MySQL Database
  -Download from: MySQL Official Site

3.JDBC MySQL Connector (.jar file)
  -Download from: MySQL Connector/J

#Database Setup

1.Open MySQL and create a database:
  -CREATE DATABASE hotel_db;

2.Create a reservations table:
  CREATE TABLE reservations (
      reservation_id INT AUTO_INCREMENT PRIMARY KEY,
      guest_name VARCHAR(255) NOT NULL,
      room_number INT NOT NULL,
      contact_number VARCHAR(20) NOT NULL,
      reservation_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
  );

#Adding JDBC Connector in VS Code
To enable Java to connect to MySQL, follow these steps:
Step 1: Download JDBC Connector
-Download mysql-connector-java-<version>.jar from MySQL Connector/J
Step 2: Add JDBC Connector to VS Code
1.Place the .jar file inside your project folder (e.g., lib/ directory).
2.Open VS Code and configure classpath:
  -Go to File → Preferences → Settings
  -Search for java.configuration.runtimes
  -Add the JDBC .jar file path under the classpath section in settings.json

3.Modify VS Code launch configuration:
  -Open .vscode/settings.json (if it doesn't exist, create it)
  -Add the following:
    {
      "java.project.referencedLibraries": [
      "lib/mysql-connector-java-<version>.jar"
      ]
    }

4.Restart VS Code to apply the changes.

#Usage Examples

1. Reserving a Room
Enter guest name: John Doe
Enter room number: 101
Enter contact number: 9876543210
Reservation successful!

2. Viewing Reservations
Current Reservations:
+----------------+-----------------+---------------+----------------------+-------------------------+
| Reservation ID | Guest           | Room Number   | Contact Number      | Reservation Date        |
+----------------+-----------------+---------------+----------------------+-------------------------+
| 1              | John Doe        | 101           | 9876543210          | 2025-02-08 10:30:00     |
+----------------+-----------------+---------------+----------------------+-------------------------+

3. Getting Room Number
Enter reservation ID: 1
Enter guest name: John Doe
Room number for Reservation ID 1 and Guest John Doe is: 101

4. Updating a Reservation
Enter reservation ID to update: 1
Enter new guest name: Jane Doe
Enter new room number: 102
Enter new contact number: 9123456789
Reservation updated successfully!

5. Deleting a Reservation
Enter reservation ID to delete: 1
Reservation deleted successfully!

#Running the Project

  1.Open the project folder in VS Code.
  2.Compile the Java file:
    -javac HotelReservationSystem.java
  3.Run the program:
    -java HotelReservationSystem

