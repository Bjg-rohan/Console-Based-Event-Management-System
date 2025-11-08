# 🎟️ Event Management System (Console-Based, Java + JDBC)

This is a **Console-Based Event Management System** developed in **Java**, using **JDBC** for database connectivity.  
The project allows **Users** to view and register for events and enables **Admins** to create, modify, and manage events through a menu-driven interface.

---

## 🚀 Features

### 👤 User Module
- View all available events
- Search events by name/date
- Register for events
- View registered events

### 🛠️ Admin Module
- Add new events
- Edit/update event details
- Delete events
- View list of users registered for events

### 🗄️ Database (MySQL + JDBC)
- Events and user registrations are stored in a database
- CRUD operations are performed through JDBC

---

## 🧱 System Architecture

| Class | Description |
|------|-------------|
| `DBConnection` | Manages database connection using JDBC. |
| `User` | Represents user details and actions like event registration. |
| `Admin` | Extends user capabilities and manages CRUD operations on events. |
| `Event` | Model class storing event properties (name, date, venue, etc.). |
| `EventManagement` | Main menu-driven console application logic. |

---

## 🛢️ Database Setup

Create a database and table in MySQL before running the project:

```sql
CREATE DATABASE eventdb;

USE eventdb;

CREATE TABLE events (
  id INT AUTO_INCREMENT PRIMARY KEY,
  event_name VARCHAR(255),
  event_date VARCHAR(255),
  event_venue VARCHAR(255)
);

CREATE TABLE registrations (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(255),
  event_id INT,
  FOREIGN KEY(event_id) REFERENCES events(id)
);
