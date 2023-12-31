# Naan Mudhalvan Backend Task - Java Spring REST API

This repository contains the backend code for the Naan Mudhalvan application implemented using the Java Spring framework. The backend is designed to fetch data from a MySQL database and provide it to a React e-commerce application.

## Table of Contents

- [Setup](#setup)
  - [Prerequisites](#prerequisites)
  - [Configuration](#configuration)
- [Endpoints](#endpoints)
- [CORS Configuration](#cors-configuration)
- [React Application Integration](#react-application-integration)
- [Contributing](#contributing)
- [License](#license)

## Setup

### Prerequisites

- Java Development Kit (JDK)
- MySQL database

### Configuration

1. Clone the repository:

   ```bash
   git clone https://github.com/Dhinesh4668/backend_java/
2. Navigate to the project directory:
   ```bash
   cd naan-mudhalvan-backend
3. Configure your MySQL database connection in the src/main/resources/application.properties file.
   spring.datasource.url=jdbc:mysql://localhost:3306/your_database
   spring.datasource.username=your_username
   spring.datasource.password=your_password
4. Build and run the Spring application:
   ```bash
   ./mvnw spring-boot:run ```
### Usage
### Endpoints
The following endpoints are available to retrieve data for the React e-commerce application:
```bash
  GET /api/products: Retrieve a list of products.
```

Example:
  ```bash
  curl http://localhost:8080/api/products
Response:
```code
  [
  {
    "id": 1,
    "name": "Product 1",
    "price": 19.99
  },
  {
    "id": 2,
    "name": "Product 2",
    "price": 29.99
  }
  // ...
]
```

### CORS Configuration
Cross-Origin Resource Sharing (CORS) is configured to allow requests from the React application. The @CrossOrigin annotation is used in the controllers, or you can configure it globally.

### React Application Integration
In your React e-commerce application, use the following methods to fetch data from the Spring backend:
  ```bash
// Fetch products
fetch('http://localhost:8080/api/products')
  .then(response => response.json())
  .then(data => {
    // Handle data in your React application
    console.log(data);
  })
  .catch(error => {
    console.error('Error fetching data:', error);
  });

  ```
