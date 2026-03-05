# Architecture Documentation for SAWT Application

## System Architecture Overview
The SAWT application follows a microservices architecture, enabling independent development and deployment of services. Each service communicates through RESTful APIs, ensuring loose coupling and high cohesion.

## Frontend Technology Stack
- **Framework:** React.js
- **State Management:** Redux
- **Styling:** CSS Modules, Bootstrap
- **Build Tools:** Webpack, Babel

## Backend Technology Stack
- **Framework:** Node.js with Express
- **Database:** MongoDB for NoSQL data and PostgreSQL for relational data handling.
- **Microservices:** Built using a combination of Node.js and Python-based services.

## Microservices
1. **User Management Service** - Handles authentication, user profiles, and authorization.
2. **Order Processing Service** - Manages the lifecycle of orders and transactions.
3. **Notification Service** - Sends emails and push notifications.
4. **Payment Gateway Service** - Integrates with various payment processors. 

## Database Schema
- **User Table:**
  - `id`: UUID (Primary Key)
  - `username`: String
  - `passwordHash`: String
- **Order Table:**
  - `id`: UUID (Primary Key)
  - `userId`: UUID (Foreign Key)
  - `productDetails`: JSON
  - `status`: String

## Deployment Architecture
- **Cloud Provider:** AWS
- **Containerization:** Docker
- **Orchestration:** Kubernetes for managing microservices.
- **Load Balancer:** AWS Elastic Load Balancing for distributing traffic.

## CI/CD Pipeline
- Tools: GitHub Actions, Docker Hub
- Steps: Code Commit -> Build -> Test -> Docker Image Creation -> Deployment to Server

## API Design Standards
- **Endpoint Structure:** RESTful structure; e.g., `/api/users`  
- **Versioning:** All APIs are versioned (e.g., `/api/v1/users`).
- **Authentication:** JWT tokens for user authentication.

## Security Measures
- **Data Encryption:** TLS/SSL for data in transit.
- **Authentication:** OAuth 2.0 for secure user login.
- **Input Validation:** All user inputs are validated and sanitized to prevent attacks.

## Scalability Strategy
- Monitored with AWS CloudWatch for scaling based on metrics (CPU, memory).
- Use of horizontal scaling for microservices using Kubernetes.

## Testing Strategy
- **Unit Testing:** Jest and Mocha for JavaScript services.
- **Integration Testing:** Postman for API testing.
- **Load Testing:** JMeter for performance testing under load.

## Conclusion
This comprehensive architecture allows the SAWT application to be scalable, maintainable, and efficient, catering to growing user demands and ensuring high availability.