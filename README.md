🚌 Online Bus Ticket Booking Application:

This is a web-based application for booking bus tickets, built using Spring Boot for the backend and Thymeleaf for the frontend. It allows users to register, log in, search for bus routes, book tickets, and view their profile and booking history. The application uses MySQL for data storage and JWT for secure authentication.

✅ Features:

User Registration and Authentication: Register and log in using email and password with JWT-based security. Bus Search: Search for available bus routes by specifying source and destination. Ticket Booking: Book tickets with passenger details and receive confirmation. User Profile: View and update personal information and view booking history. Responsive UI: Built with Thymeleaf and Bootstrap for a modern, responsive design.

🚀 Technologies Used:

Backend: Spring Boot, Spring Data JPA, Spring Security, JWT Frontend: Thymeleaf, Bootstrap Database: MySQL

📑 Prerequisites:

Java 17 or later Maven MySQL Postman (for API testing) Setup Instructions git clone https://github.com/your-repo/bus-booking.git cd bus-booking

⚙️ Configure MySQL:

Update src/main/resources/application.properties with your MySQL credentials:spring.datasource.url=jdbc:mysql://localhost:3306/busbooking spring.datasource.username=root spring.datasource.password=yourpassword spring.jpa.hibernate.ddl-auto=update spring.jpa.show-sql=true spring.thymeleaf.cache=false

Build and Run the Application: mvn clean install mvn spring-boot:run

The application will be accessible at http://localhost:8080. 🔐 Swagger Documentation http://localhost:8080/swagger-ui/index.html

Access the Application: Open a browser and navigate to http://localhost:8080/users/register to create a new account. Log in at http://localhost:8080/users/login. Search for buses at http://localhost:8080/buses/search.

API Endpoints:

The application exposes RESTful APIs for programmatic access. Below are the key endpoints: POST /users/register: Register a new user Request Body: { "name": "John Doe", "email": "john@example.com", "password": "password" } Response: User object POST /users/login: Authenticate a user and return a JWT token Request Body: { "email": "john@example.com", "password": "password" } Response: { "token": "jwt-token" } GET /buses/search?fromLocation=CityA&toLocation=CityB: Search for buses Response: List of available buses POST /buses/book: Book a bus ticket Request Body: { "busId": 1, "seatNumber": "A1", "passengerName": "Jane Doe", "passengerAge": 30, "passengerGender": "Female" } Response: Booking confirmation

Using Postman for API Testing:

Install Postman: Download and install Postman from https://www.postman.com/. Test Registration: Create a new POST request to http://localhost:8080/users/register. Set the request body to JSON:{ "name": "John Doe", "email": "john@example.com", "password": "password" } Send the request and verify the response. Test Login: Create a new POST request to http://localhost:8080/users/login. Set the request body to JSON:{ "email": "john@example.com", "password": "password" } Copy the JWT token from the response. Test Protected Endpoints: For endpoints like /buses/book, add the JWT token in the Authorization header as Bearer .

🧪 Running Tests:

Run unit tests using Maven: mvn test

📂 Project Structure::::::::::::

bus-booking/

├── src/

│ ├── main/

│ │ ├── java/

│ │ │ ├── com/

│ │ │ │ ├── busbooking/

│ │ │ │ │ ├── config/

│ │ │ │ │ │ ├── SecurityConfig.java

│ │ │ │ │ │ ├── SwaggerConfig.java

│ │ │ │ │ ├── controller/

│ │ │ │ │ │ ├── AuthController.java

│ │ │ │ │ │ ├── BookingController.java

│ │ │ │ │ │ ├── BusSearchController.java

│ │ │ │ │ │ ├── CustomErrorController.java

│ │ │ │ │ │ ├── UserController.java

│ │ │ │ │ ├── dto/

│ │ │ │ │ │ ├── BookingRequestDTO.java

│ │ │ │ │ │ ├── BusSearchDTO.java

│ │ │ │ │ │ ├── ChangePasswordDTO.java

│ │ │ │ │ │ ├── PassengerDTO.java

│ │ │ │ │ │ ├── UserProfileUpdateDTO.java

│ │ │ │ │ │ ├── UserRegistrationDTO.java

│ │ │ │ │ ├── entity/

│ │ │ │ │ │ ├── Booking.java

│ │ │ │ │ │ ├── Bus.java

│ │ │ │ │ │ ├── Passenger.java

│ │ │ │ │ │ ├── Route.java

│ │ │ │ │ │ ├── User.java

│ │ │ │ │ ├── repository/

│ │ │ │ │ │ ├── BookingRepository.java

│ │ │ │ │ │ ├── BusRepository.java

│ │ │ │ │ │ ├── PassengerRepository.java

│ │ │ │ │ │ ├── RouteRepository.java

│ │ │ │ │ │ ├── UserRepository.java

│ │ │ │ │ ├── service/

│ │ │ │ │ │ ├── BookingService.java

│ │ │ │ │ │ ├── BusService.java

│ │ │ │ │ │ ├── RouteService.java

│ │ │ │ │ │ ├── UserDetailsServiceImpl.java

│ │ │ │ │ │ ├── UserService.java

│ │ │ │ │ ├── Application.java

│ │ │ ├── resources/

│ │ │ │ ├── static/

│ │ │ │ │ ├── css/

│ │ │ │ │ │ ├── styles.css

│ │ │ │ ├── templates/

│ │ │ │ │ ├── booking-form.html

│ │ │ │ │ ├── bus-list.html

│ │ │ │ │ ├── error.html

│ │ │ │ │ ├── history.html

│ │ │ │ │ ├── home.html

│ │ │ │ │ ├── login.html

│ │ │ │ │ ├── register.html

│ │ │ │ │ ├── profile.html

│ │ │ │ │ ├── search.html

│ │ │ │ ├── application.properties

│ ├── test/

│ │ ├── java/ │ │ │ ├── com/ │ │ │ │ ├── busbooking/ │ │ │ │ │ ├── BusBookingApplicationTest │ ├── pom.xml
About

springBoot,thymeleaf,and css property,maven project
Resources
Readme
Activity
Stars
0 stars
Watchers
0 watching
Forks
0 forks
Releases
No releases published
Create a new release
Packages
No packages published
Publish your first package
Languages

Java 57.7%

    HTML 42.3% 

Suggested workflows
Based on your tech stack

    Publish Java Package with Gradle logo
    Publish Java Package with Gradle

Build a Java Package using Gradle and publish to GitHub Packages.
SLSA Generic generator logo
SLSA Generic generator
Generate SLSA3 provenance for your existing release workflows
Java with Maven logo
Java with Maven

    Build and test a Java project with Apache Maven.

More workflows
Footer




✅ Part 1: Project Setup in Eclipse::

Create Spring Boot Project

Use https://start.spring.io

Select:

Project: Maven

Language: Java

Dependencies: Spring Web, Spring Data JPA, PostgreSQL Driver

Download & import in Eclipse

Project Structure

css
Copy
Edit
└── src
    ├── main
    │   ├── java
    │   │   └── com.example.demo
    │   │       ├── DemoApplication.java
    │   │       ├── controller/
    │   │       ├── service/
    │   │       └── model/
    │   └── resources
    │       ├── application.properties
    │       └── static/templates (for UI)
    
✅ Part 2: Add PostgreSQL Support:

In application.properties:

properties
Copy
Edit
spring.datasource.url=jdbc:postgresql://localhost:5432/mydb
spring.datasource.username=postgres
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
⚠️ DB name = mydb — create it in PostgreSQL first
Use tools like pgAdmin or terminal:
CREATE DATABASE mydb;

✅ Part 3: Add Docker Support:

Create a file in root: Dockerfile

dockerfile
Copy
Edit
FROM openjdk:17-jdk-slim
VOLUME /tmp
ARG JAR_FILE=target/demo-0.0.1-SNAPSHOT.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]
Build JAR

bash
Copy
Edit
./mvnw clean package

✅ Part 4: Create GitHub Repo & Push Code:

Initialize git:

bash
Copy
Edit
git init
git add .
git commit -m "initial commit"
Push to GitHub:

bash
Copy
Edit
git remote add origin https://github.com/your-username/your-repo.git
git push -u origin main

✅ Part 5: Deploy on Render:

Go to https://render.com → New → Web Service

Select:

Connect your GitHub repo

Environment: Docker

Region: Closest to user (e.g., Singapore)

Name: bus-booking-app

Add build command:
No need (Render will use Dockerfile)

Add PostgreSQL DB:
Go to Render → Dashboard → PostgreSQL → Create New
Copy:

DB URL → paste in Render service's environment variables

✅ Part 6: Replace application.properties with Render DB
properties:

Copy
Edit
spring.datasource.url=${DB_URL}
spring.datasource.username=${DB_USER}
spring.datasource.password=${DB_PASSWORD}
spring.jpa.hibernate.ddl-auto=update
Render automatically injects these via environment variables.

✅ Part 7: Done

App deploy hote hi URL milega like:
https://bus-booking-app.onrender.com
----------------------------------------------------------------------------------------------------------------------------
