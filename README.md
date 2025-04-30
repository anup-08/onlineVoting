# Online Voting System

A secure web application for voter registration, candidate management, and real-time election tracking built with Spring Boot (backend) and React (frontend).

## Features
- ✅ Voter registration with email validation
- 🗳️ Candidate nomination and party management
- 🔒 Secure ballot casting with fraud prevention
- 📊 Real-time election results dashboard
- 👨‍💻 Admin oversight panel

## Tech Stack
**Backend**  
Spring Boot
Spring Data JPA
MySQL

**Frontend**  
React
Bootstrap

## Setup Guide

### 1. Database Configuration
sql
CREATE DATABASE voting_db;
CREATE USER 'votezy_user'@'localhost' IDENTIFIED BY 'securepassword123';
GRANT ALL PRIVILEGES ON voting_db.* TO 'votezy_user'@'localhost';
FLUSH PRIVILEGES;

### 2. Backend Setup

cd online-voting-system

# Configure database (edit src/main/resources/application.properties)
spring.datasource.url=jdbc:mysql://localhost:3306/voting_db
spring.datasource.username=votezy_user
spring.datasource.password=securepassword123

# Build and run
mvn clean install
mvn spring-boot:run

### 3. Frontend Setup

cd src/main/resources/static

# Install dependencies
npm install

# Launch development server
npm start

### 4. Deployment

# Package as executable JAR
mvn package -DskipTests
java -jar target/Votezy-0.0.1-SNAPSHOT.jar

# Docker build
docker build -t votezy-app .
docker run -p 8080:8080 votezy-app
