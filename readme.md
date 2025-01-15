Stokify - A Virtual Stock Market Assistant
Table of Contents
Project Overview
Features
Technologies Used
Installation
Usage
Database Schema
Contributors
References
Project Overview
Stokify is a Java-based virtual stock market assistant designed to simplify the process of managing investments, tracking stock performance, and staying informed about market trends. The project aims to provide both novice and experienced investors with a user-friendly platform to manage portfolios, buy and sell stocks, and view real-time market data.

Features
User Login and Registration
Secure login using a unique username and password.
New users can register by providing personal and financial details.
Stock Search
Search stocks by name or NSE code.
View stock price, yearly highs and lows, and other relevant details.
User Dashboard
Profile Management: View user details like name, wallet balance, and government IDs.
Portfolio Management: Track investments, quantities, and average prices.
Buy Stocks: Purchase stocks directly and update portfolio and wallet.
Sell Stocks: Sell stocks, update wallet balance, and manage portfolio.
Market Prices
Real-time stock prices from NSE and BSE.
Account Management
Wallet management for real-time balance updates.
Secure user logout.
Technologies Used
Programming Language: Java (JDK 8+)
Database: MySQL
Database Connectivity: JDBC (Java Database Connectivity)
IDE: IntelliJ IDEA / Eclipse
Installation
Prerequisites
Install Java JDK 8+.
Install MySQL Server.
Install a MySQL client like MySQL Workbench or CLI.
Use an IDE like IntelliJ IDEA or Eclipse.
Steps to Setup
Clone the repository:

bash
Copy code
git clone ~https://github.com/your_username/Stokify.git~  
cd stokify  
Import the project into your IDE.

Create the MySQL database and tables using the provided schema in database/schema.sql.

Configure the database connection in the Stokify class:

java
Copy code
String url = "jdbc:mysql://localhost:3306/your_database_name";  
String user = "your_username";  
String password = "your_password";  
Build and run the project.

Usage
Start the application and choose from the main menu:

Register as a new user or log in as an existing user.
Use the dashboard to manage your portfolio, buy/sell stocks, and view real-time market trends.
Navigate using the menu options displayed in the CLI.

Database Schema
Tables
Users Table
Stores user information such as username, email, and wallet balance.

sql
Copy code
CREATE TABLE Users (  
    UserID INT AUTO_INCREMENT PRIMARY KEY,  
    Username VARCHAR(50) NOT NULL UNIQUE,  
    Email VARCHAR(100) NOT NULL UNIQUE,  
    WalletBalance FLOAT NOT NULL,  
    AadhaarNumber VARCHAR(12) UNIQUE NOT NULL,  
    PAN VARCHAR(10) UNIQUE NOT NULL  
);  
Stock Table
Stores stock details like price, yearly highs/lows, and trading codes.

sql
Copy code
CREATE TABLE Stock (  
    StockID INT AUTO_INCREMENT PRIMARY KEY,  
    CompanyName VARCHAR(100),  
    StockPrice FLOAT,  
    YearHigh FLOAT,  
    YearLow FLOAT,  
    NSECode VARCHAR(10) UNIQUE NOT NULL,  
    BSECode VARCHAR(10) UNIQUE NOT NULL  
);  
Portfolio Table
Tracks user investments and stock quantities.

sql
Copy code
CREATE TABLE Portfolio (  
    PortfolioID INT AUTO_INCREMENT PRIMARY KEY,  
    UserID INT,  
    StockID INT,  
    Quantity INT,  
    FOREIGN KEY (UserID) REFERENCES Users(UserID),  
    FOREIGN KEY (StockID) REFERENCES Stock(StockID)  
);  
Contributors
Rishabh Chaurasia (AF0465296)
Rocky Kumar Singh (AF0465507)
Ritik Gupta (AF0465502)
Project Mentor: Sahil Kaushik (Anudip Foundation)

References
National Stock Exchange of India (NSE)
Bombay Stock Exchange (BSE)
Java Documentation
MySQL Documentation
JDBC Documentation