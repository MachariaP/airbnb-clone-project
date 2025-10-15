<div align="center">
  <h1>🏠 Airbnb Clone Project</h1>
  <p>A scalable backend for a booking platform inspired by Airbnb</p>

![GitHub repo size](https://img.shields.io/github/repo-size/MachariaP/airbnb-clone-project)
  ![GitHub last commit](https://img.shields.io/github/last-commit/MachariaP/airbnb-clone-project)
  ![License](https://img.shields.io/github/license/MachariaP/airbnb-clone-project)
</div>

---

## 📋 Project Overview
The **Airbnb Clone Project** is a full-stack applications designed to replicate
core Airbnb functionalities, including user management, property listings, bookings, and reviews.
This project focuses on building a robust, secure, and scalable backend using modern technologies to deliver a seamless user and host experience.


### 🎯 Project Goals
- **User Management**: Secure registration, authentication, and profile management.
- **Property Management**: Create, Update, and Retrive property listings.
- **Booking System**: Facilitate property reservations with check-in/check-out management.
- **Payment Processing**: Handle secure payment transactions.
- **Review System**: Enable users to post and manage property reviews.
- **Data Optimization**: Optimize data retrieval and storage with indexing and caching.

---

##  🛠️ Technology Stack
| Technology                | Purpose                               |
|---------------------------|---------------------------------------|
| **Django**                | Python web framework for building secure and scalable RESTful APIs. |
| **Django REST Framework** | Simplifies API development with tools for CRUD operations. |
| **PostgreSQL**            | Relational database for storing user, property, and booking data. |
| **GraphQL**               | Flexible query language for efficient, client-driven data retrieval. |
| **Celery**                | Handles asynchronous tasks like notifications and payment processing. |
| **Redis**                 | Supports caching and session management to enhance performance. |
| **Docker**                | Ensures consistent development and deployment environments. |
| **CI/CD Pipelines**       | Automates testing and deployment using tools like GitHub Actions.|

---

## 👥 Team Roles
| Role                  | Responsibilities                                |
|-----------------------|-------------------------------------------------|
| **Backend Developer** | Implements API endpoints, database schemas, and business logic for core features. |
| **Database Adimn**    | Designs and optimizes PostgreSQL schemas, implements indexing for performance. |
| **DevOps Engineer**   | Manages deployment, scaling, and monitoring using Docker and CI/CD pipelines. |
| **QA Engineer**       | Tests backend functionalities to ensure reliability, security, and quality. |

---

## 🗄️ Database Design
The database is structured using **PostgreSQL** to manage key entities and their relationships.

| Entity      | Key Fields                       | Relationships           |
|-------------|----------------------------------|-------------------------|
| **Users**   | `user_id` (PK), `email`, `password_hash`, `name`, `phone` | Owns multiple properties; creates bookings/review (1:N). |
| **Properties** | `property_id` (PK), `owner_id` (FK), `title`, `description`, `price_per_night` | Belongs to one user; has multiple bookings/reviews (1:N). |
| **Bookings** | `booking_id` (PK), `user_id` (FK), `property_id` (FK), `check_in_date`, `check_out_date` | Belongs to one user and one property (N:1). |
| **Review** | `review_id` (PK),`user_id` (FK), `property_id` (FK), `rating`, `comment` | Belongs to one user and one property (N:1). |
| **Payments** | `payment_id` (PK), `booking_id` (FK), `amount`, `payment_date`, `status` | Belongs to one booking (N:1). |

---
