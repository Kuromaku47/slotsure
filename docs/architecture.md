## 1. Who uses SlotSure?
-Customers 
-Employees 
-Owner

## 2.What client do they interact with?
-Customers interact with the mobile app or web browser
-Employees interact with the web browser
-Owner interacts with the web browser

## 3. What receives their request?
-Backend API receives requests from clients

## 4. What major backend components exist?
-Authentication "user signup and login"
-Services "What services the user provides"
-Bookings "Appointments tht customers can make"
-Availability "Which staffs are available at that time"
-Database "Stores users profiles"

## 5. Where is the databse?
-The databse is PostgreSQL hosted on AWS

## 6. Where should the booking consistency logic live?
-In the database and Backend API

## 7. Architecture Diagram

```mermaid
graph TD
    %% Users (Question 1)
    Customer[Customer]
    Employee[Employee]
    Owner[Owner]

    %% Clients (Question 2)
    MobileApp[Mobile App]
    WebBrowser[Web Browser]

    %% What receives the request (Question 3)
    API[Backend API]

    %% Backend Components (Question 4 & 6)
    Auth[Authentication]
    Services[Services]
    Bookings[Bookings <br/>-- Consistency Logic here]
    Availability[Availability]

    %% Database (Question 5 & 6)
    DB[(PostgreSQL on AWS)]

    %% How they connect (The Arrows)
    Customer --> MobileApp
    Customer --> WebBrowser
    Employee --> WebBrowser
    Owner --> WebBrowser

    MobileApp --> API
    WebBrowser --> API

    API --> Auth
    API --> Services
    API --> Bookings
    API --> Availability

    Auth --> DB
    Services --> DB
    Bookings --> DB
    Availability --> DB
```