# NHA-098: Ajarly Educational Platform

A comprehensive full-stack educational management system built with modern web technologies. This project consists of a React/TypeScript frontend and a Spring Boot backend API.

## 📋 Project Overview

Ajarly is an educational platform that provides tools for managing courses, campuses, departments, and user authentication. The system supports multiple user roles (students, instructors, administrators) with an intuitive interface and robust backend infrastructure.

---

## 🏗️ Project Architecture

```
NHA-098/
├── Frontend/                 # React + TypeScript frontend application
│   ├── src/                 # Source code
│   ├── public/              # Static assets
│   ├── package.json         # Frontend dependencies
│   ├── vite.config.ts       # Vite configuration
│   ├── jest.config.js       # Jest testing configuration
│   └── README.md            # Frontend-specific documentation
│
└── Backend/                 # Spring Boot backend API
    ├── src/                 # Source code
    ├── pom.xml              # Maven dependencies and build configuration
    ├── ajarly-query.sql     # Database queries
    ├── ajarly_schema.sql    # Database schema
    ├── .env                 # Environment variables (Git ignored)
    └── .gitignore           # Git ignore rules
```

---

## 🚀 Quick Start

### Prerequisites

#### Frontend
- **Node.js** >= 16.0.0
- **npm** >= 7.0.0 or **yarn** >= 1.22.0

#### Backend
- **Java** 17 or higher
- **Maven** >= 3.6.0
- **MySQL** 5.7+ or MariaDB 10.3+

### Installation & Running

#### Frontend Setup

```bash
cd Frontend

# Install dependencies
npm install

# Start development server (runs on http://localhost:5173)
npm run dev

# Build for production
npm run build

# Run tests
npm test
```

#### Backend Setup

```bash
cd Backend

# Install dependencies and build
mvn clean install

# Run the application (runs on http://localhost:8080)
mvn spring-boot:run

# Or package and run JAR
mvn clean package
java -jar target/backend-0.0.1-SNAPSHOT.jar
```

---

## 📦 Frontend Tech Stack

### Core
- **React** 18.3.1 - UI library
- **TypeScript** - Type-safe JavaScript
- **Vite** 6.3.5 - Build tool & dev server
- **React Router DOM** 7.9.6 - Client-side routing

### UI & Styling
- **Tailwind CSS** - Utility-first CSS framework
- **Radix UI** - Unstyled, accessible components
  - Dialogs, Dropdowns, Tooltips, Selects, Tabs, Accordions, etc.
- **Lucide React** - Icon library
- **Class Variance Authority** - Type-safe component variants
- **Sonner** - Toast notifications

### Components & Features
- **Embla Carousel** 8.6.0 - Carousel/slider
- **React Resizable Panels** 2.1.7 - Resizable layouts
- **Next Themes** 0.4.6 - Dark mode support
- **Recharts** 2.15.2 - Charting/visualization
- **React Hook Form** 7.55.0 - Form state management
- **React Day Picker** 8.10.1 - Date selection
- **Date-fns** - Date utilities


### Testing
- **Jest** 30.2.0 - Testing framework
- **ts-jest** - Jest + TypeScript support

---

## 💾 Backend Tech Stack

### Core Framework
- **Spring Boot** 3.2.0 - Java application framework
- **Spring Web** - REST API support
- **Spring Security** - Authentication & authorization
- **Java** 17 - Latest stable Java LTS

### Database
- **MySQL/MariaDB** - Database
- Schema and sample queries provided in SQL files

### External Services
- **Cloudinary** 2.0.0 - Cloud image/video storage and management

### Utilities
- **Lombok** 1.18.30 - Reduce boilerplate code
- **dotenv-java** 2.2.4 - Environment variable management

---

## 🗄️ Database Setup

### Schema
The `ajarly_schema.sql` file contains all table definitions and relationships.

### Import Schema

```bash
# Using MySQL CLI
mysql -u root -p < Backend/ajarly_schema.sql

# Or using MySQL Workbench/DataGrip - import the SQL file directly
```

### Database Configuration

Update `Backend/.env`:

```env
SPRING_DATASOURCE_URL=jdbc:mysql://localhost:3306/ajarly
SPRING_DATASOURCE_USERNAME=root
SPRING_DATASOURCE_PASSWORD=your_password
```

---

## ⚙️ Environment Configuration

### Frontend
Environment variables can be set in `.env.local` (create if needed):

```env
VITE_API_URL=http://localhost:8080
VITE_ENVIRONMENT=development
```

### Backend
Environment variables in `Backend/.env`:

```env
# Database
SPRING_DATASOURCE_URL=jdbc:mysql://localhost:3306/ajarly
SPRING_DATASOURCE_USERNAME=root
SPRING_DATASOURCE_PASSWORD=root

# Server
SERVER_PORT=8080
SPRING_JPA_HIBERNATE_DDL_AUTO=update

# Cloudinary (for image uploads)
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Security
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRATION=86400000
```

---

## 📝 Available Commands

### Frontend

```bash
npm run dev              # Start development server
npm run build            # Build for production
npm run preview          # Preview production build locally
npm test                 # Run tests once
npm run test:watch      # Run tests in watch mode
npm run test:coverage   # Generate test coverage report
npm run test:verbose    # Run tests with detailed output
```

### Backend

```bash
mvn clean install        # Download dependencies and build
mvn spring-boot:run      # Run the application
mvn test                 # Run unit tests
mvn clean package        # Create JAR file in target/
mvn compile              # Compile source code only
mvn verify               # Run all tests and validation
mvn dependency:tree      # View dependency tree
```

---

## 🌐 API Endpoints

### Base URL
```
http://localhost:8080/api
```


---

## 🧪 Testing

### Frontend

```bash
# Run all tests
npm test

# Watch mode for TDD
npm run test:watch

# Generate coverage report
npm run test:coverage

# Verbose output with test names
npm run test:verbose

# Test a specific file
npm test -- ComponentName
```

**Test Configuration:** `jest.config.js` and `jest.setup.js`

### Backend

```bash
# Run all tests
mvn test

# Skip tests during build
mvn clean install -DskipTests

# Run specific test
mvn test -Dtest=UserControllerTest

# Generate test report
mvn surefire-report:report
```

---

## 📂 Project Structure

### Frontend (`/Frontend/src`)
```
src/
├── components/       # Reusable React components
├── pages/           # Page components for routes
├── hooks/           # Custom React hooks
├── context/         # React Context API providers
├── utils/           # Utility functions and helpers
├── types/           # TypeScript type definitions
├── styles/          # Global styles
└── api/             # API client and endpoints
```

### Backend (`/Backend/src/main/java/com/ajarly`)
```
├── controller/      # REST API endpoints
├── service/         # Business logic
├── repository/      # Database access (JPA)
├── model/          # Entity classes
├── dto/            # Data Transfer Objects
├── config/         # Spring configuration
├── exception/      # Custom exceptions
└── util/           # Helper utilities
```

---

## 🚢 Deployment

### Frontend Deployment

Build and deploy the static files:

```bash
npm run build
# dist/ folder contains all files to deploy
```

**Hosting Options:**
- Vercel (recommended for React/Vite)
- Netlify
- GitHub Pages
- AWS S3 + CloudFront
- Azure Static Web Apps

### Backend Deployment

Package as JAR and deploy:

```bash
mvn clean package
# target/backend-0.0.1-SNAPSHOT.jar is ready
```

**Hosting Options:**
- AWS EC2 / ElasticBeanstalk
- Heroku
- DigitalOcean
- Google Cloud Run
- Azure App Service
- On-premises servers

### Docker Support (Optional)

Create `Dockerfile` for backend:

```dockerfile
FROM openjdk:17-jdk-slim
COPY target/backend-0.0.1-SNAPSHOT.jar app.jar
ENTRYPOINT ["java","-jar","/app.jar"]
```

```bash
docker build -t ajarly-backend .
docker run -p 8080:8080 ajarly-backend
```

---

## 🔍 Code Quality

### Frontend Linting
```bash
# ESLint and TypeScript checking is configured
npm run lint       # (if configured)
```

### Backend Code Quality
```bash
# SonarQube integration (if configured)
mvn sonar:sonar
```

---

## 📦 Dependency Management

### Updating Dependencies

**Frontend:**
```bash
npm outdated              # Check for updates
npm update                # Update dependencies
npm install package@^x.y.z  # Install specific version
```

**Backend:**
```bash
mvn versions:display-dependency-updates  # Check for updates
mvn versions:use-latest-versions        # Update to latest
```

---

## 🐛 Troubleshooting

### Frontend Issues

**Port 5173 already in use:**
```bash
npm run dev -- --port 3000  # Use different port
```

**Module not found errors:**
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

**TypeScript compilation errors:**
```bash
npm run build  # Check build errors before deployment
```

### Backend Issues

**Database connection errors:**
- Verify MySQL is running: `mysql -u root -p`
- Check `.env` credentials match your setup
- Ensure database `ajarly` exists

**Port 8080 already in use:**
```bash
# Change in application.properties or .env:
SERVER_PORT=8081
```

**Cloudinary upload errors:**
- Verify API keys in `.env`
- Check Cloudinary account status

---

## 📚 Documentation

- [Frontend README](./Frontend/README.md) - Frontend-specific documentation
- [Backend Configuration](./Backend/.env) - Backend environment setup
- [Database Schema](./Backend/ajarly_schema.sql) - Database structure
- [API Queries](./Backend/ajarly-query.sql) - Sample database queries

---

## 🔐 Security

### Best Practices Implemented

- **Spring Security** - Authentication & authorization
- **CORS Configuration** - Controlled cross-origin access
- **Password Encryption** - Secure password storage
- **Environment Variables** - Sensitive data not in code
- **JWT Tokens** - Stateless authentication (if implemented)

### Security Checklist Before Deployment

- [ ] Change default passwords
- [ ] Update `.env` with production values
- [ ] Enable HTTPS in production
- [ ] Set `SPRING_JPA_HIBERNATE_DDL_AUTO=validate`
- [ ] Review CORS settings
- [ ] Add rate limiting
- [ ] Enable logging and monitoring

---


---

## 📋 Checklist for Production

- [ ] Frontend build optimized (`npm run build`)
- [ ] Backend packaged as JAR (`mvn clean package`)
- [ ] Environment variables configured for production
- [ ] Database backed up
- [ ] SSL/HTTPS certificate installed
- [ ] Cloudinary credentials secured
- [ ] Monitoring and logging configured
- [ ] Error handling and user feedback tested
- [ ] Performance tested under load
- [ ] Security vulnerabilities scanned

---

## 📞 Support & Contact

For issues, questions, or suggestions:

1. **GitHub Issues** - Create an issue on the repository
2. **Email** - Contact the development team
3. **Documentation** - Check existing docs and guides

---

## 📄 License

This project is proprietary software. All rights reserved. Unauthorized copying, distribution, or modification is prohibited without explicit written permission.

---

## 🎯 Project Status

- **Version:** 1.0.0 (Development)
- **Frontend:** 0.1.0
- **Backend:** 0.0.1-SNAPSHOT
- **Status:** Active Development
- **Last Updated:** December 2024

---

## 🔗 Useful Links

### Documentation
- [React Documentation](https://react.dev)
- [Spring Boot Documentation](https://spring.io/projects/spring-boot)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Vite Documentation](https://vitejs.dev)
- [Maven Documentation](https://maven.apache.org/guides/)

### Tools & Services
- [Cloudinary Documentation](https://cloudinary.com/documentation)
- [MySQL Documentation](https://dev.mysql.com/doc/)
- [Postman](https://www.postman.com/) - API testing

---

## 👨‍💻 Technology Stack Summary

| Layer | Technology | Version |
|-------|-----------|---------|
| **Frontend Framework** | React | 18.3.1 |
| **Frontend Language** | TypeScript | - |
| **Build Tool** | Vite | 6.3.5 |
| **UI Framework** | Tailwind CSS + Radix UI | - |
| **Backend Framework** | Spring Boot | 3.2.0 |
| **Language** | Java | 17 |
| **Database** | MySQL/MariaDB | 5.7+ |
| **Package Manager (Frontend)** | npm | 7.0+ |
| **Build Tool (Backend)** | Maven | 3.6.0+ |

---

**Made with ❤️ by the Development Team**
