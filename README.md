 # Payana: Tours and Travels Management System                                                                                      
  
  A desktop-based Travel and Tourism Management System built with Java Swing and MySQL. Allows customers to browse, book hotels and    tour packages, and provides an admin panel to manage listings.                                                                     

  ## Features

  - User registration and login with password recovery
  - Admin dashboard for managing hotels and tour packages
  - Hotel browsing and booking with AC/Non-AC and food options
  - Tour package browsing and booking
  - Customer profile management
  - View booking history for hotels and packages

  ## Tech Stack

  | Technology | Purpose |
  |------------|---------|
  | Java Swing (AWT) | Desktop GUI |
  | MySQL 8.0 | Database |
  | JDBC | Database connectivity |
  | JCalendar | Date picker component |
  | rs2xml | ResultSet to table mapping |
  | Apache Ant | Build system |

  ## Prerequisites

  - Java JDK 16 or higher
  - MySQL Server 8.0
  - Apache Ant (optional, for building from source)

  ## Installation

  ### 1. Clone the repository

  ```bash
  git clone https://github.com/rizwanpatel-gif/Payana.git
  cd Payana

  2. Set up the database

  Open MySQL and run the following:

  CREATE DATABASE IF NOT EXISTS ttms;
  USE ttms;

  CREATE TABLE account(username VARCHAR(50), name VARCHAR(50), password VARCHAR(50), security VARCHAR(50), answer VARCHAR(50));      
  CREATE TABLE admin(name VARCHAR(50), username VARCHAR(50), password VARCHAR(50), email VARCHAR(50), phone VARCHAR(50), pancard     
  VARCHAR(50));
  CREATE TABLE customer(name VARCHAR(50), username VARCHAR(50), password VARCHAR(50), email VARCHAR(50), phone VARCHAR(50), pancard  
  VARCHAR(50));
  CREATE TABLE adminlogin(username VARCHAR(50), password VARCHAR(50));
  CREATE TABLE bookhotel(hotelname VARCHAR(50), name VARCHAR(50), username VARCHAR(50), persons VARCHAR(50), days VARCHAR(50),       
  ac_nonac VARCHAR(50), food VARCHAR(50), totalprice VARCHAR(50));
  CREATE TABLE bookpackage(place VARCHAR(50), name VARCHAR(50), username VARCHAR(50), persons VARCHAR(50), date VARCHAR(50),
  totalprice VARCHAR(50));
  CREATE TABLE hotel(name VARCHAR(50), state VARCHAR(50), ac VARCHAR(50), food VARCHAR(50), hotelcost VARCHAR(50), image LONGBLOB);  
  CREATE TABLE package(place VARCHAR(50), state VARCHAR(50), price VARCHAR(50), days_nights VARCHAR(50), description LONGTEXT, image 
  LONGBLOB);

  3. Configure database credentials

  Update the connection details in src/travel/management/system/Conn.java:

  c = DriverManager.getConnection("jdbc:mysql:///ttms", "root", "your-password");

  4. Compile and run

  javac -cp "src/jcalendar-1.4.jar;rs2xml.jar;jcalendar-tz-1.3.3-4.jar" -d build/classes src/travel/management/system/*.java

  java -cp "build/classes;src/jcalendar-1.4.jar;rs2xml.jar;jcalendar-tz-1.3.3-4.jar" travel.management.system.Front

  Or open the project in NetBeans IDE and click Run.

  Usage

  1. Launch the application -- the splash screen appears
  2. Click Next to go to the home page
  3. Sign Up to create a new customer account
  4. Login with your credentials to access the customer dashboard
  5. Browse available hotels and packages, and make bookings
  6. Use Admin Login to access the admin panel for managing hotels and packages

  Project Structure

  src/travel/management/system/
  ├── Front.java              # Splash screen (entry point)
  ├── Home.java               # Main home page
  ├── Login.java              # Customer login
  ├── Signup.java             # Customer registration
  ├── ForgotPassword.java     # Password recovery
  ├── Conn.java               # MySQL database connection
  ├── AdminLogin.java         # Admin login
  ├── AdminHome.java          # Admin dashboard
  ├── CustomerHome.java       # Customer dashboard
  ├── AddHotel.java           # Add hotel (admin)
  ├── AddPackage.java         # Add package (admin)
  ├── BookHotel.java          # Book a hotel
  ├── BookPackage.java        # Book a package
  ├── HotelPanel.java         # Hotel listing panel
  ├── HotelDetails.java       # Hotel details view
  ├── PackagePanel.java       # Package listing panel
  ├── PackageDetails.java     # Package details view
  ├── BookedHotelPanel.java   # View hotel bookings
  ├── BookedPackagePanel.java # View package bookings
  ├── AllCustomerPanel.java   # All customers (admin)
  ├── HomePanel.java          # Home page panel
  ├── ProfilePanel.java       # User profile
  └── icons/                  # Image assets

  Troubleshooting

  Access denied for MySQL

  Make sure the password in Conn.java matches your MySQL root password.

  Application closes immediately

  Ensure the icons/ folder with all image assets is present inside build/classes/travel/management/system/. The app loads images from
   the classpath at runtime.

  ClassNotFoundException for MySQL driver

  Add the MySQL Connector JAR to your classpath. Download it from the MySQL website if missing.

  License

  This project is for educational purposes.
