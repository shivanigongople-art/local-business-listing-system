# Local Business Listing System

A full-stack web application to **list, search and manage local businesses** (restaurants, shops, clinics, services, etc.), built with **Spring Boot, Spring Data JPA and MySQL**, with a responsive HTML/CSS/JavaScript frontend.

## Features

- Add, view, update and delete business listings (CRUD)
- Search businesses by keyword (name / description)
- Filter by category and city
- Results sorted by rating
- Input validation (required fields, 10-digit phone, email format, rating 0–5)
- Global exception handling with clean JSON error responses
- Automatic `createdAt` / `updatedAt` timestamps

## Tech Stack

| Layer     | Technology                              |
|-----------|-----------------------------------------|
| Backend   | Java 17, Spring Boot 3, Spring Data JPA |
| Database  | MySQL 8                                 |
| Frontend  | HTML5, CSS3, JavaScript (Fetch API)     |
| Build     | Maven                                   |

## Project Structure

```
src/main/java/com/shivani/businesslisting
├── LocalBusinessListingApplication.java
├── controller/BusinessController.java
├── entity/Business.java
├── exception/GlobalExceptionHandler.java
├── exception/ResourceNotFoundException.java
├── repository/BusinessRepository.java
└── service/BusinessService.java
src/main/resources
├── application.properties
└── static/index.html
```

## Getting Started

### Prerequisites
- Java 17+
- Maven 3.8+
- MySQL 8

### Run locally

1. Clone the repository
   ```bash
   git clone https://github.com/<your-username>/local-business-listing-system.git
   cd local-business-listing-system
   ```
2. Update your MySQL username and password in `src/main/resources/application.properties`.
   The database `business_listing_db` is created automatically.
3. Run the application
   ```bash
   mvn spring-boot:run
   ```
4. Open **http://localhost:8080** in your browser.

## REST API Endpoints

| Method | Endpoint                         | Description                          |
|--------|----------------------------------|--------------------------------------|
| GET    | `/api/businesses`                | Get all businesses                   |
| GET    | `/api/businesses/{id}`           | Get business by ID                   |
| POST   | `/api/businesses`                | Add a new business                   |
| PUT    | `/api/businesses/{id}`           | Update a business                    |
| DELETE | `/api/businesses/{id}`           | Delete a business                    |
| GET    | `/api/businesses/search?keyword=&category=&city=` | Search & filter     |
| GET    | `/api/businesses/categories`     | List all categories                  |
| GET    | `/api/businesses/cities`         | List all cities                      |

### Sample request

```json
POST /api/businesses
{
  "name": "Sai Krupa Restaurant",
  "category": "Restaurant",
  "description": "Authentic Maharashtrian thali and snacks",
  "address": "Shivaji Nagar, Main Road",
  "city": "Nanded",
  "phone": "9876543210",
  "email": "saikrupa@example.com",
  "openingHours": "10 AM - 11 PM",
  "rating": 4.5
}
```

## Author

**Shivani**
