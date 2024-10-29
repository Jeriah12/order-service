# order-service

The **order-service** manages the shopping cart, order placement, and order tracking functionalities within the e-commerce platform.

## Table of Contents

- [Features](#features)
- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [API Endpoints](#api-endpoints)
- [Testing](#testing)


## Features

- **Shopping Cart Management:** Allows users to add products to a cart, update quantities, and remove items.
- **Order Placement: Facilitates:** the process of submitting an order.
- **Order Tracking:** Enables users to track the status of their orders.

## Technology Stack

- **Language:** Java
- **Framework:** Spring Boot
- **Database:** MySQL
- **Containerization:** Docker

## Prerequisites

Before you begin, ensure you have met the following requirements:

* Java JDK 11 or higher
* Maven or Gradle
* MySQL 8.0 or higher
* Docker
* Git for version control

## Installation

Follow these steps to set up the Order Service on your local machine:

1. ***Clone the repository:***

```bash
git clone https://github.com/your-username/order-service.git
cd order-service
```
2. ***Build the project:***

```bash
mvn clean install
```

3. ***Environment Variables:***

Create an application.properties file in src/main/resources/ and add the following properties:

```properties
server.port=8080
spring.datasource.url=jdbc:mysql://localhost:3306/orderdb
spring.datasource.username=your_username
spring.datasource.password=your_password
```

4. ***Running Docker:***

Build the Docker image:

```bash
docker build -t order-service:latest .
```

5. ***Run the Docker container:***

```bash
docker run -p 8080:8080 --env-file .env order-service:latest
```
The service should now be accessible at http://localhost:8080

## API Endpoints

**Create a new order**
* Endpoint: POST /api/orders
* Description: Places a new order.
  ```bash
  {
  "userId": "user123",
  "products": [
    {
      "productId": "product456",
      "quantity": 2
    },
    {
      "productId": "product789",
      "quantity": 1
    }
   ]
  }
  ```
  
**Get order by ID** 
* Endpoint: GET /api/orders/{order_id}

**Get order by User ID** 
* Endpoint: GET /api/orders/{userid}
  
**Update Order**
* Endpoint: PUT http://localhost:3001/orders/{id}
  
**Delete Order**
* Endpoint: DELETE http://localhost:3001/orders/{id}
  
## Testing
Run unit tests using:

```bash
mvn test
```
This command will execute all tests located in the tests directory.
