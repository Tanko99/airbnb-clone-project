# airbnb-clone-project

## Project Overview.
The airbnb clone project is a simplified airbnb patform designed for a robust and scalable operation and involves; user management, property listings, booking management, payment processing, reviews of property and data optimisation.

---

## Project Goals
-  Build a user-friendly and responsive interface.
- Implement secure user authentication (sign-up, login, session management).
- Allow users to list, search, and book properties.
- Create RESTful APIs for listing management and booking functionality.
- Connect the frontend to a backend server and a database.
- Deploy both frontend and backend for public access.

---

## Tech Stack
### Frontend:
- **Reaxt with typescript** or **Next.JS**
-  **HTML5**, **CSS3**, **Tailwind CSS**
-   **React  Router**

### Backend:
- **Django**
-  **Python**, **JavaSceipt**, **MySQL**.
-  **Docker**, **CI/CD Pipelines**

---

## Team Roles.
|Role                    |Function                                                       |Responsability in the project                                                          
|------------------------|---------------------------------------------------------------|----------------------------------------------------------------------------------------|
|Product Manager |Makes sure a product or its part is delivered on time and within budget and also motivates the software development team|Will over that product is produced on time
|UI/UX Designer|Transforms a product vision into user-friendly designs|Will ensure the user interface is functioning well and intuitive to satisfy user needs and their experiences
|Backend Developer|Implements the core of an application-its algorithms and business logic|Responsible for implementing API endpoints, database schemas, and business logic.
|Frontend Developer|create the part of an application that users interact with, ensuring that an app offers an equally smooth experience to all|Responsible for the client side
|DevOps Engineer|Builds continuous integration and continuous delivery (CI/CD) pipelines for faster delivery|Handles deployment, monitoring, and scaling of the backend services.
|Quality Assurance Engineer|Makes sure an application performs according to requirements and spots functional/non-functional defects|Ensures the best quality standards for the app
|Dtabase Administrator|Mnages the Database|Manages the database design. Indexing and optimisation

---

## Technology Stack 
|stack                      |Role in the project
|---------------------------|-------------------------------------------------------------------------------------------
|Django|   A high-level Python web framework used for building the RESTful API.
|Django REST Framework|    Provides tools for creating and managing RESTful APIs.
|PostgreSQL|    A powerful relational database used for data storage.
|GraphQL|       Allows for flexible and efficient querying of data.
|Celery|        For handling asynchronous tasks such as sending notifications or processing payments.
|Redis|          Used for caching and session management.
|Docker|           Containerization tool for consistent development and deployment environments.
|CI/CD Pipelines|     Automated pipelines for testing and deploying code changes.
|HTML5|            An advanced HTML that will be  Used for building the structure of web pages with semantic markup.
|Tailwind CSS|       Will be used for styling user interface components quickly using uti;ity-first classes
|React|            Used to create interactuve and reusable user intefface componenets
|Next.JS|       Used as the react framework for routing, Server Side Rendering(SSR) and perform.--

---
## Database Design

## 1. **User**
 This represents someone who can host or book properties.

### Key Fields:
- `id` (Primary Key)
- `name`
- `email` (Unique)
- `passwordHash`
- `role` (e.g., guest, host)

### Relationships:
- A user can create **multiple properties** (if they are a host).
- A user can make **multiple bookings**.
- A user can leave **multiple reviews**.

---

## 2. **Property**
Represents a listing available for booking.

### Key Fields:
- `id` (Primary Key)
- `title`
- `description`
- `location`
- `pricePerNight`
- `hostId` (Foreign Key → User)

### Relationships:
- A property is **owned by one user** (host).
- A property can have **many bookings**.
- A property can have **many reviews**.

---

## 3. **Booking**
Represents a reservation made by a user for a property.

### Key Fields:
- `id` (Primary Key)
- `userId` (Foreign Key → User)
- `propertyId` (Foreign Key → Property)
- `startDate`
- `endDate`
- `totalPrice`

### Relationships:
- A booking is made by **one user**.
- A booking is for **one property**.
- A booking can have **one payment**.

---

## 4. **Review**
Represents feedback given by a user for a property.

### Key Fields:
- `id` (Primary Key)
- `userId` (Foreign Key → User)
- `propertyId` (Foreign Key → Property)
- `rating` (e.g., 1–5)
- `comment`

### Relationships:
- A review is written by **one user**.
- A review is for **one property**.
- A user can leave **one review per property per booking** (enforce this via logic/constraints).

---

## 5. **Payment**
Represents a payment transaction for a booking.

### Key Fields:
- `id` (Primary Key)
- `bookingId` (Foreign Key → Booking)
- `amount`
- `status` (e.g., paid, pending, failed)
- `paymentMethod` (e.g., card, PayPal, MTN momo, Orange money or any other payment method)

### Relationships:
- A payment is linked to **one booking**.
- A booking has **one payment** (one-to-one).

---
## Feature Breakdown
This project includes the following features;
## 1. User Management
Handles user registration, login/logout, profile editing, and role-based access (e.g., guests vs. hosts).
Ensures secure access and personalized experiences for users. It allows hosts to list properties and guests to make bookings, forming the backbone of user interaction within the system.

---

## 2. Property Management
Enables hosts to create, update, and delete property listings. This includes adding descriptions, prices, photos, availability, and location data.
Provides a platform for hosts to showcase their accommodations and manage listings efficiently, making properties discoverable for potential guests.

---

## 3. Booking System
Manages reservation processes including date selection, availability checks, booking confirmations, and cancellations.
Facilitates the core transaction between guests and hosts by allowing seamless scheduling and reservation of properties, ensuring proper handling of availability and conflicts.

---

## 4. Data Optimization

Includes database indexing, caching, and query optimization to improve the performance and scalability of the application. 
Enhances the responsiveness and efficiency of the platform, particularly under high user traffic, ensuring a smooth and scalable user experience.

---

## 5. Reviews 
Allows guests to rate and review properties and hosts, and optionally allows hosts to review guests.  
Builds trust and community credibility by providing transparent feedback, helping users make informed decisions and encouraging quality service.

---

## 6. Payment Processing
Handles secure transactions between guests and hosts, including integration with third-party payment gateways (e.g., Stripe, PayPal).
Enables the monetization aspect of the platform, supporting safe and reliable financial interactions that are essential for the functioning of a real-world marketplace.

---








