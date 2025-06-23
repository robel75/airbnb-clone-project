# airbnb-clone-project

## Overview

The Airbnb Clone Project is a full-stack web application that replicates key functionalities of Airbnb, including property listings, user authentication, booking, and payment features. The goal is to provide hands-on experience in designing and developing a scalable and secure real-world web platform.

---

## Team Roles

- Frontend Developer: Designs and implements the user interface using modern JavaScript frameworks and ensures responsiveness and accessibility.
- Backend Developer: Builds RESTful APIs using Django, manages business logic, and handles authentication, authorization, and validation.
- Database Administrator (DBA): Designs and manages the PostgreSQL database, optimizing queries and ensuring data integrity.
- DevOps Engineer: Sets up CI/CD pipelines, manages Docker containers, and ensures deployment and scaling using cloud services.
- QA Engineer: Writes and executes test cases to ensure the quality and stability of features through manual and automated testing.

---

## Technology Stack

- Django: A high-level Python web framework for building secure and scalable backend APIs.
- PostgreSQL: A robust relational database system to store user, property, booking, and payment data.
- GraphQL: An API query language for efficient and flexible data fetching from the frontend.
- Docker: Used to containerize the application for consistent development and deployment.
- GitHub Actions: For automating tests, builds, and deployments via CI/CD pipelines.

---

## Database Design

### Key Entities:

1. User
   - id (Primary Key)
   - name
   - email
   - password_hash
   - role (guest/host)

2. Property
   - id
   - title
   - description
   - location
   - host_id (Foreign Key to User)

3. Booking
   - id
   - property_id
   - user_id
   - start_date
   - end_date

4. Review
   - id
   - user_id
   - property_id
   - rating
   - comment

5. Payment
   - id
   - booking_id
   - amount
   - payment_method
   - status

### Relationships:
- A User can be a host (listing properties) or a guest (booking properties).
- A Property belongs to one host.
- A Booking is made by a guest for a property.
- A Review is submitted by a guest for a property.
- A Payment is linked to a Booking.

---

## Feature Breakdown

- User Management: Includes user registration, login, profile management, and role assignment (guest or host).
- Property Management: Hosts can list properties with details, images, and pricing. Guests can view and filter listings.
- Booking System: Guests can book available properties for specific dates, and hosts can manage incoming bookings.
- Review System: Guests can leave ratings and comments on properties they’ve stayed at.
- Payment Integration: Secure online payment processing for bookings with status tracking and confirmation emails.

---

## API Security

- Authentication: Users must log in using secure password hashing and session/token management.
- Authorization: Ensures that only hosts can list/edit their properties and only guests can book.
- Rate Limiting: Protects the API from abuse by limiting the number of requests per user/IP.
- Input Validation: Prevents malicious input, SQL injection, and XSS attacks.
- Data Privacy: Encrypt sensitive data and protect user credentials and payment info.

Security is essential for protecting user accounts, securing financial transactions, and maintaining trust in the platform.

---

## CI/CD Pipeline

CI/CD (Continuous Integration/Continuous Deployment) automates the process of testing, building, and deploying code.

### Tools:
- GitHub Actions: Automatically runs tests and checks after each commit/push.
- Docker: Ensures that the same environment is used during development and production.
- Heroku / AWS / Render: Can be used to deploy the app continuously after successful builds.
