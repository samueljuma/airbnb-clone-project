# 🏠 Airbnb Clone Project

A backend API for an Airbnb-style booking platform, built with Django and GraphQL.

---

## 🚀 Objective

Build a robust, scalable backend system that supports core Airbnb functionalities including user accounts, listings, bookings, payments, and reviews.

---

## 🏆 Project Goals

- **User Management** – Registration, authentication (JWT), and profile updates
- **Property Management** – Listing creation, updates, and search
- **Booking System** – Property reservations and scheduling
- **Payment Processing** – Integration for handling transactions
- **Review System** – Users can rate and review properties
- **Optimization** – Indexing, caching, and database performance

---

## ⚙️ Technology Stack

| #            | Tools and Technologies    |
|--------------|---------------------------|
| Language     | Python 3.11+              |
| Framework    | Django, Django REST Framework, GraphQL (Strawberry/Graphene) |
| Database     | PostgreSQL                |
| Auth         | JWT (SimpleJWT)           |
| Async Tasks  | Celery + Redis            |
| Containerization | Docker                |
| CI/CD        | GitHub Actions / Others   |

---

## 📖 API Design

Supports both REST (via DRF) and GraphQL endpoints.

---

## 👥 Team Roles

This project involves multiple roles that contribute to building and maintaining the backend system:

| Role                | Responsibility                                                                 |
|---------------------|----------------------------------------------------------------------------------|
| **Backend Developer**     | Builds the API endpoints, integrates business logic, ensures authentication and security mechanisms are properly implemented. |
| **Database Administrator (DBA)** | Designs the database schema, manages indexing and performance optimization, and ensures data integrity. |
| **DevOps Engineer**        | Sets up Docker environments, manages CI/CD pipelines, handles deployment and monitoring of the application. |
| **QA Engineer**            | Writes test cases, performs manual and automated testing to ensure the backend meets quality standards. |

---

## 🧱 Technology Stack

| Technology       | Purpose                                                                                  |
|------------------|------------------------------------------------------------------------------------------|
| **Python**       | The primary programming language used for building the backend logic.                    |
| **Django**       | High-level web framework for handling routing, models, authentication, and admin.       |
| **Django REST Framework** | Simplifies building RESTful APIs with features like serializers and viewsets.         |
| **GraphQL**      | Enables flexible and efficient client-defined queries and mutations.                     |
| **PostgreSQL**   | Relational database used to store structured data like users, bookings, and listings.    |
| **JWT (SimpleJWT)** | Provides stateless, token-based authentication for securing API access.                |
| **Celery**       | Manages asynchronous tasks such as sending emails or processing payments.                |
| **Redis**        | Acts as a message broker for Celery and handles caching for improved performance.        |
| **Docker**       | Containers to isolate services and ensure consistent environments across machines.       |
| **CI/CD Pipelines** | Automates testing, building, and deployment processes for continuous delivery.         |


---

## 🗃️ Database Design

The backend system is designed around several core entities. Below is an overview of each entity, key fields, and relationships.

| Entity      | Key Fields                                             | Relationships                                                                 |
|-------------|--------------------------------------------------------|--------------------------------------------------------------------------------|
| **User**    | `id`, `name`, `email`, `password`, `is_host`          | A user can list multiple properties and make multiple bookings.                |
| **Property**| `id`, `title`, `description`, `location`, `price`     | A property belongs to one host (User) and can have multiple bookings/reviews. |
| **Booking** | `id`, `user_id`, `property_id`, `check_in`, `check_out` | A booking is made by a user for a specific property.                          |
| **Review**  | `id`, `user_id`, `property_id`, `rating`, `comment`   | A review is posted by a user for a specific property.                         |
| **Payment** | `id`, `booking_id`, `amount`, `status`, `payment_method` | A payment is tied to a booking.                                               |

---

## 🧩 Feature Breakdown

| Feature               | Description                                                                                                   |
|------------------------|---------------------------------------------------------------------------------------------------------------|
| **User Management**    | Enables users to register, log in using JWT, and manage their profile. Includes host identification and account settings. |
| **Property Management**| Hosts can create, update, and manage property listings including details like title, price, location, and availability. |
| **Booking System**     | Allows users to browse available properties, make reservations, view booking history, and manage check-in/check-out. |
| **Payment Processing** | Securely handles payments for bookings via integrated payment gateways. Payment records are linked to bookings. |
| **Review System**      | Users can leave reviews and rate properties after a completed booking. Reviews help maintain trust in the platform. |
| **API Support**        | RESTful and GraphQL APIs provide flexible access to data for frontend clients or third-party integrations.     |
| **Asynchronous Tasks** | Background tasks (e.g., email notifications, payment confirmations) are handled using Celery and Redis.        |
| **Data Optimization**  | Utilizes caching and indexing to speed up frequent queries and reduce load on the database.                   |
