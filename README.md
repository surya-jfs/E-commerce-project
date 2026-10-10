# E-Commerce Website

A full-stack e-commerce application with a React frontend and a Java Spring Boot backend. The backend uses Spring Data JPA and MySQL, with Spring Security and JWT-related classes for authentication.

## Tech Stack

### Frontend
- React
- Vite
- React Router
- Axios
- Bootstrap
- React Icons

### Backend
- Java 17
- Spring Boot
- Spring Web MVC
- Spring Data JPA
- Spring Security
- JSON Web Tokens (JJWT)
- Maven

### Database
- MySQL

## Project Structure

The repository contains two applications: `e-commerce/` for the backend and `react-e-commerce/` for the frontend.

```text
E-commerce-project/
├── README.md
├── .vscode/
├── e-commerce/                         # Spring Boot backend
│   ├── pom.xml
│   ├── mvnw
│   ├── mvnw.cmd
│   └── src/
│       ├── main/
│       │   └── java/com/example/e_commerce/
│       │       ├── ECommerceApplication.java
│       │       ├── controller/          # REST controllers
│       │       │   ├── AdminController.java
│       │       │   ├── AuthController.java
│       │       │   ├── ProductController.java
│       │       │   └── Products.java
│       │       ├── service/             # Business logic
│       │       │   └── ProductService.java
│       │       ├── repository/          # JPA repositories
│       │       │   ├── ProductRepository.java
│       │       │   └── UserRepository.java
│       │       ├── entity/              # JPA entities
│       │       │   ├── Product.java
│       │       │   └── User.java
│       │       ├── dto/                 # Data transfer objects
│       │       │   ├── AuthRequest.java
│       │       │   └── ProductResponse.java
│       │       ├── cart/                # Cart domain
│       │       │   ├── Cart.java
│       │       │   ├── CartItem.java
│       │       │   ├── CartController.java
│       │       │   ├── CartService.java
│       │       │   ├── CartRepository.java
│       │       │   └── dto/
│       │       │       ├── CartItemDTO.java
│       │       │       └── CartResponseDTO.java
│       │       ├── order/               # Order domain
│       │       │   ├── OrderController.java
│       │       │   ├── OrderService.java
│       │       │   ├── OrderRepository.java
│       │       │   ├── OrderItemRepository.java
│       │       │   ├── Orders.java
│       │       │   └── OrderItem.java
│       │       └── security/            # Security and JWT classes
│       │           ├── SecurityConfig.java
│       │           ├── JwtFilter.java
│       │           ├── JwtUtil.java
│       │           ├── HashPassword.java
│       │           └── CustomUserDetailsService.java
│       └── test/
│           └── java/com/example/e_commerce/
│               └── ECommerceApplicationTests.java
└── react-e-commerce/                    # React + Vite frontend
    ├── package.json
    ├── package-lock.json
    ├── index.html
    ├── vite.config.js
    └── src/
        ├── App.jsx
        ├── App.css
        ├── main.jsx
        ├── index.css
        ├── assets/
        └── components/
            ├── admin/
            ├── api/                     # API helper modules
            ├── cart/
            ├── login/
            ├── navbar/
            ├── products/
            ├── protectedroute/
            ├── register/
            ├── search/
            └── user/
```

The tree above highlights the main files and packages; some folders contain additional files. Database scripts and a root-level screenshots folder are not currently included in this structure.

## Prerequisites

Install the following before running the project:
- JDK 17
- MySQL
- Node.js and npm
- Git

The backend uses the Maven Wrapper, so a separate Maven installation is generally not required.

## Setup and Run

### 1. Clone the repository

```bash
git clone https://github.com/surya-jfs/E-commerce-project.git
cd E-commerce-project
```

### 2. Configure MySQL

Create a MySQL database for the application. For example:

```sql
CREATE DATABASE ecommerce_db;
```

Configure the datasource URL, username, and password for your local MySQL instance in the Spring Boot configuration. If you use an `application.properties` file, place it at:

`e-commerce/src/main/resources/application.properties`

Example configuration (replace the username and password with your own values):

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/ecommerce_db
spring.datasource.username=YOUR_MYSQL_USERNAME
spring.datasource.password=YOUR_MYSQL_PASSWORD
```

Do not commit real database passwords or other secrets to GitHub.

### 3. Run the Spring Boot backend

Open a terminal in the repository root.

On Windows:

```powershell
cd e-commerce
.\mvnw.cmd spring-boot:run
```

On macOS/Linux:

```bash
cd e-commerce
chmod +x mvnw
./mvnw spring-boot:run
```

Keep the backend terminal running. Check the application logs for startup errors and the port on which the server starts.

### 4. Run the React frontend

Open a second terminal from the repository root:

```bash
cd react-e-commerce
npm install
npm run dev
```

Open the local URL printed by Vite in the terminal.

## Main Application Areas

The repository includes frontend components and backend classes for:
- User registration and login
- Product browsing and search
- Shopping cart
- Orders
- Admin-related functionality
- Backend security and JWT handling

The exact available operations depend on the implemented endpoints and current application configuration.

## Development Commands

Run these commands from `react-e-commerce/`:

```bash
npm run dev     # Start the Vite development server
npm run build   # Build the frontend for production
npm run lint    # Run ESLint
npm run preview # Preview the production build locally
```

## Troubleshooting

- **Backend cannot connect to MySQL:** Verify that MySQL is running, the database exists, and the datasource credentials are correct.
- **Frontend API requests fail:** Confirm the backend is running and check the API base URL in the frontend API helper files.
- **Frontend dependencies are missing:** Run `npm install` from `react-e-commerce/`.
- **Backend does not start:** Check that JDK 17 is installed and review the Maven/Spring Boot error output.

## Future Improvements

Possible additions include documenting API endpoints, adding screenshots, writing more automated tests, and providing deployment instructions.

## Author

Surya

## Repository

https://github.com/surya-jfs/E-commerce-project
