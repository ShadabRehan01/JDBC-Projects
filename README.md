
# 🧾 Java-Based Management Systems (Hospital & Banking)

This repository contains two Java console-based projects:

1. 🏥 **Hospital Management System**
2. 🏦 **Banking Management System**

Both systems use **Java + JDBC + MySQL** and follow clean OOP practices. Ideal for learning backend development and database interaction.

---

## 🏥 Hospital Management System

### ✅ Features

- Add new patient
- View all patients
- View doctors
- Book appointments with doctors
- Check doctor availability before booking

### 🛠️ Technologies Used

- Java
- JDBC (Java Database Connectivity)
- MySQL Database
- IntelliJ IDEA / Eclipse

### 📂 Java Files

- `HospitalManagementSystem.java` – Main class with interactive menu
- `Patient.java` – Add/view patients and check patient by ID
- `Doctor.java` – View doctors and validate doctor ID

### 🗃️ Database Tables

```sql
CREATE TABLE patients (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    age INT,
    gender VARCHAR(10)
);

CREATE TABLE doctors (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    specialization VARCHAR(100)
);

CREATE TABLE appointments (
    id INT PRIMARY KEY AUTO_INCREMENT,
    patient_id INT,
    doctor_id INT,
    appointment_date DATE,
    FOREIGN KEY(patient_id) REFERENCES patients(id),
    FOREIGN KEY(doctor_id) REFERENCES doctors(id)
);
```

---

## 🏦 Banking Management System

### ✅ Features

- User registration and login
- Account creation with PIN
- Deposit and withdraw money
- Transfer money between accounts
- View balance and transaction history
- SQL transaction rollback on failures

### 🛠️ Technologies Used

- Java
- JDBC
- MySQL Database
- IntelliJ IDEA / Eclipse

### 📂 Java Files

- `User.java` – Handles registration, login, and user existence checks
- `Bank.java` – Deposit, withdraw, transfer money, view balance, transaction history
- `Main.java` – Main class to start the application

### 🗃️ Database Tables

```sql
CREATE TABLE User (
    id INT PRIMARY KEY AUTO_INCREMENT,
    full_name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(100)
);

CREATE TABLE Account (
    account_number BIGINT PRIMARY KEY,
    user_id INT,
    balance DOUBLE,
    pin INT,
    FOREIGN KEY(user_id) REFERENCES User(id)
);

CREATE TABLE Transaction (
    id INT PRIMARY KEY AUTO_INCREMENT,
    sender_account BIGINT,
    receiver_account BIGINT,
    amount DOUBLE,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## 🚀 How to Run

1. Clone this repository.
2. Create the database and tables in MySQL using the provided SQL.
3. Open the project in IntelliJ IDEA or Eclipse.
4. Update DB credentials in each Java file.
5. Compile and run the main classes:
   - `HospitalManagementSystem.java` (for Hospital)
   - `Main.java` (for Banking)

---

## 👨‍💻 Author

Shadab Rehan
📍 India
🔗 LinkedIn Profile - https://www.linkedin.com/in/shadabrehan
---

## 📌 Note

These projects are for learning purposes and basic simulations. You can extend them by adding features like:

- GUI or Web interface
- Password hashing and validation
- Admin and role-based access
- Advanced transaction features

---

## 📎 License

This project is open source and free to use for educational purposes.
