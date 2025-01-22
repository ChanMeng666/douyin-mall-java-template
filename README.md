# Douyin Mall Java Template

A Spring Boot-based e-commerce platform template project with microservice architecture. This template provides basic project structure and configurations for those who want to start building their own e-commerce application.

## Table of Contents

- [Technology Stack](#technology-stack)
- [Prerequisites](#prerequisites)
- [Project Creation Guide](#project-creation-guide)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Common Issues](#common-issues)
- [Contributing](#contributing)
- [License](#license)

## Technology Stack

### Core Framework
- **Spring Boot**: 3.4.1
- **JDK**: 17
- **Build Tool**: Maven 3.6+

### Data Storage
- **MySQL**: 5.7+
- **Redis**: 6.0+
- **Spring Data JPA**
- **MyBatis**

### Microservice Architecture
- **Spring Cloud Alibaba**
- **Spring Cloud Gateway**
- **Spring Cloud Config**
- **Spring Cloud Eureka**

### Message Queue
- **RabbitMQ**: 3.8+

### Security
- **Spring Security**
- **JWT**
- **OAuth2**

### Others
- **Docker**: 20.10+
- **AI Integration Support**
- **Quartz Scheduler**
- **Spring Mail**

## Prerequisites

Before you start, ensure you have the following installed:
- JDK 17 or later
- Maven 3.6+
- MySQL 5.7+
- IDE (Recommended: IntelliJ IDEA)
- Git

## Project Creation Guide

### Step 1: Create Project Using IntelliJ IDEA

1. Open IntelliJ IDEA
2. Click "New Project"
3. Select "Spring Initializr"
4. Configure project metadata:
   ```
   Group: com.douyinmall
   Artifact: douyin-mall-java-template
   Name: douyin-mall-java-template
   Description: Douyin Mall Java Template Project
   Package name: com.douyinmall.mall
   Packaging: Jar
   Java version: 17
   ```

### Step 2: Select Dependencies

Choose the following Spring Boot dependencies:

1. **Core Dependencies**:
   - Spring Web
   - Spring Boot DevTools
   - Lombok
   - Spring Configuration Processor

2. **Data Access**:
   - Spring Data JPA
   - MySQL Driver
   - Spring Data Redis
   - MyBatis Framework

3. **Security**:
   - Spring Security
   - OAuth2 Resource Server
   - Spring Session

4. **Messaging**:
   - Spring for RabbitMQ

5. **Cloud Dependencies**:
   - Eureka Discovery Client
   - Config Client
   - Gateway
   - Resilience4j

6. **Others**:
   - Spring Boot Actuator
   - Validation
   - Java Mail Sender
   - Quartz Scheduler

### Step 3: Basic Configuration

Create `application.properties` in `src/main/resources`:

```properties
# Application
spring.application.name=douyin-mall
server.port=8080

# Database
spring.datasource.url=jdbc:mysql://localhost:3306/douyin_mall?useUnicode=true&characterEncoding=utf8&serverTimezone=Asia/Shanghai
spring.datasource.username=root
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA
spring.jpa.database-platform=org.hibernate.dialect.MySQLDialect
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update
spring.jpa.open-in-view=false

# Disable Services Initially
spring.autoconfigure.exclude=\
  org.springframework.boot.autoconfigure.data.redis.RedisAutoConfiguration,\
  org.springframework.boot.autoconfigure.data.redis.RedisRepositoriesAutoConfiguration,\
  org.springframework.boot.autoconfigure.amqp.RabbitAutoConfiguration

# Eureka Client
eureka.client.enabled=false
```

### Step 4: Create Database

```sql
CREATE DATABASE douyin_mall CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

### Step 5: Project Structure

Create the following package structure:

```
src/main/java/com/douyinmall/mall
├── config/
├── controller/
├── service/
│   └── impl/
├── repository/
├── entity/
├── dto/
├── vo/
├── utils/
└── DouyinMallApplication.java
```

## Running the Application

1. Build the project:
   ```bash
   mvn clean package
   ```

2. Run the application:
   ```bash
   java -jar target/douyin-mall-java-template-0.0.1-SNAPSHOT.jar
   ```

Or run directly in IDE by running the main class `DouyinMallApplication.java`.

## Common Issues

### 1. JDK Version Mismatch
If you see JDK version issues, ensure:
- JDK 17 is installed
- Project structure settings use JDK 17
- Maven compiler settings are configured for Java 17

### 2. Database Connection Issues
- Verify MySQL is running
- Check database credentials
- Ensure database 'douyin_mall' exists

### 3. Port Conflicts
If port 8080 is occupied, modify `server.port` in application.properties

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the Apache-2.0 License - see the LICENSE.md file for details.

---

**Note**: This template is designed for educational and reference purposes. Remember to configure proper security measures before deploying to production.
