# Inventory Management System

A robust RESTful Inventory Management System built using **Spring Boot 3** and **MongoDB**. The application provides complete CRUD operations for Suppliers, Categories, Products, and Orders, along with automated stock management, order processing, validation, and exception handling.

---

## Author

**Vyom Desai**  
Registration Number: **24BCE10318**  
B.Tech Computer Science and Engineering

---

## Project Overview

The Inventory Management System helps organizations manage inventory efficiently by maintaining product records, supplier information, categories, and customer orders. The system automatically updates stock levels during order creation, modification, and deletion while ensuring data consistency and validation.

---

## Features

- Supplier Management (CRUD)
- Category Management (CRUD)
- Product Management (CRUD)
- Order Management (CRUD)
- Automatic Stock Deduction
- Stock Restoration on Order Deletion
- Order Total Calculation
- Validation using Jakarta Bean Validation
- Global Exception Handling
- Swagger/OpenAPI Documentation
- MongoDB Database Integration

---

## Technology Stack

| Layer | Technology |
|---------|------------|
| Backend | Spring Boot 3 |
| Language | Java 17 |
| Database | MongoDB |
| API Documentation | Swagger/OpenAPI |
| Build Tool | Maven |
| Validation | Jakarta Validation |
| Boilerplate Reduction | Lombok |

---

## Project Structure

```text
src/main/java/com/inventory
│
├── controller
├── service
├── serviceimpl
├── repository
├── model
├── dto
│   ├── request
│   └── response
├── exception
├── config
└── InventoryManagementApplication.java
```

---

## MongoDB Relationships

```text
Supplier (1) ---------- (N) Product

Category (1) ---------- (N) Product

Order (1) ---------- (N) OrderItem

Product (M) ---------- (N) Order
```

---

## Business Logic

| Scenario | Behaviour |
|-----------|-----------|
| Create Order | Validates product availability and deducts stock |
| Update Order | Restores previous stock and revalidates new quantities |
| Delete Order | Restores stock automatically |
| Insufficient Stock | Returns appropriate error response |
| Duplicate Supplier Email | Returns HTTP 409 Conflict |
| Duplicate Category Name | Returns HTTP 409 Conflict |
| Total Amount | Automatically calculated |

---

## Prerequisites

- Java 17 or higher
- Maven 3.8+
- MongoDB 6.0+

---

## Installation & Setup

### Clone Repository

```bash
git clone <repository-url>
cd inventory-management
```

### Configure MongoDB

Update `application.properties`

```properties
spring.data.mongodb.uri=mongodb://localhost:27017/inventorydb
```

### Build Project

```bash
mvn clean install
```

### Run Application

```bash
mvn spring-boot:run
```

Application will start at:

```text
http://localhost:8080
```

---

## API Documentation

After starting the application:

### Swagger UI

```text
http://localhost:8080/swagger-ui.html
```

### OpenAPI Specification

```text
http://localhost:8080/api-docs
```

---

## REST API Modules

| Module | Endpoints |
|----------|----------|
| Suppliers | Create, Read, Update, Delete |
| Categories | Create, Read, Update, Delete |
| Products | Create, Read, Update, Delete |
| Orders | Create, Read, Update, Delete |

---

## Sample Endpoints

### Supplier APIs

```http
POST   /api/v1/suppliers
GET    /api/v1/suppliers
GET    /api/v1/suppliers/{id}
PUT    /api/v1/suppliers/{id}
DELETE /api/v1/suppliers/{id}
```

### Category APIs

```http
POST   /api/v1/categories
GET    /api/v1/categories
GET    /api/v1/categories/{id}
PUT    /api/v1/categories/{id}
DELETE /api/v1/categories/{id}
```

### Product APIs

```http
POST   /api/v1/products
GET    /api/v1/products
GET    /api/v1/products/{id}
PUT    /api/v1/products/{id}
DELETE /api/v1/products/{id}
```

### Order APIs

```http
POST   /api/v1/orders
GET    /api/v1/orders
GET    /api/v1/orders/{id}
PUT    /api/v1/orders/{id}
DELETE /api/v1/orders/{id}
```

---

## Error Handling

The application provides standardized error responses for:

- Resource Not Found (404)
- Validation Errors (400)
- Insufficient Stock (400)
- Duplicate Resources (409)
- Internal Server Errors (500)

---

## Future Enhancements

- JWT Authentication
- Role-Based Access Control
- Pagination and Sorting
- Dashboard Analytics
- Inventory Reports
- Email Notifications
- Docker Deployment
- Unit & Integration Testing

---

## Learning Outcomes

This project demonstrates practical implementation of:

- Spring Boot REST APIs
- MongoDB Database Operations
- DTO Pattern
- Layered Architecture
- Exception Handling
- Validation
- Business Logic Implementation
- API Documentation using Swagger

---

## License

This project is developed for educational and learning purposes.