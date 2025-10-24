Web Based Banking System
A simple yet functional Web-Based Banking System developed as a Y2S1 Software Engineering project. Built with Java 23, Spring Boot 3.x, Spring Data JPA, Thymeleaf for frontend templates, Tailwind CSS for styling, and MySQL for the database. Features include role-based access (Customer, Staff, Admin), CRUD operations for accounts, transactions (with OTP simulation), loans, users, Fix Deposit and feedback, real-time balance updates, transaction history with CSV export, and secure login/logout with BCrypt hashing. Ideal for demonstrating MVC architecture, JPA entity management, and basic security in a university setting.

--Tools and Technologies--
Programming Language - Java 23
Framework - Spring Boot 3.x
Frontend - Thymeleaf with Tailwind CSS
Database - MySQL with JPA/Hibernate
Security - Spring Security with BCrypt
IDE - IntelliJ IDEA Ultimate
Build Tool - Maven
Other - Lombok, Apache Commons CSV, Spring Boot DevTools

--Setup Instructions--
Follow these steps to set up and run the project on your local machine.

--Prerequisites--
Java JDK 23 installed (verify with java -version)
MySQL Server 8.0+ installed (verify with mysql --version)
MySQL Workbench installed for DB management
IntelliJ IDEA Ultimate

Step 1- Set Up MySQL Database

Open MySQL Workbench and connect to your local server (host: localhost, port: 3306, user: root, password: your_password).


Create the empty database (run this query in a new tab and execute),
"CREATE DATABASE IF NOT EXISTS bank_db;"
Note - There isn’t a manual schema SQL script in this project. With spring.jpa.hibernate.ddl-auto=update in application.properties, Hibernate inspects the mapped entities on startup and automatically creates any missing tables/columns (and applies simple alterations) in the existing bank_db schema. You do not need to write or run SQL queries for tables—the first run of the app will build out the tables for you without a manual SQL file, as long as the database exists and the user has the right permissions. Refresh schemas in Workbench after running the app to see the tables (user, account, transaction, loan, feedback).


Step 2 - Import the Project in IntelliJ IDEA

Open IntelliJ IDEA Ultimate.
Click "Open" on the welcome screen > Select your project folder (Bank-Project).
When prompted, import as Maven project (click OK/Import).
Set JDK - File > Project Structure > Project SDK > Select JDK 23.
Enable annotation processing for Lombok: File > Settings > Build > Compiler > Annotation Processors > Check "Enable annotation processing".
Update application.properties in src/main/resources - Set spring.datasource.password to your MySQL root password.

Step 3 - Build and Run

Reload Maven - Right-click pom.xml > Maven > Reload Project (wait for dependencies to download).
Build - Build > Rebuild Project (ensure 0 errors).
Run - Right-click BankingSystemApplication.java > Run (console shows "Started... Tomcat on 8080").
Access - Browser > http://localhost:8080/login. (Create your own admin and bankstaff)


Troubleshooting

DB connection fail - Check application.properties password and MySQL service running.
Reds in code - Reload Maven, rebuild.
Error page - Check console logs for details.
