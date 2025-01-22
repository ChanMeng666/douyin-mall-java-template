<div align="center">
 <h1>🛍️ Douyin Mall Java Template<br/><small>A Production-Ready E-commerce Platform</small></h1>
 <img src="https://img.shields.io/badge/spring%20boot-3.4.1-brightgreen.svg"/>
 <img src="https://img.shields.io/badge/JDK-17-blue.svg"/>
 <img src="https://img.shields.io/badge/maven-3.6%2B-important.svg"/>
 <img src="https://img.shields.io/badge/mysql-5.7%2B-blue.svg"/>
 <img src="https://img.shields.io/badge/redis-6.0%2B-red.svg"/>
</div>

> [!IMPORTANT]
> This is a production-ready template project built with Spring Boot and microservice architecture. While it demonstrates industry best practices, please thoroughly review and enhance security measures before deploying to production.

# 🌟 Introduction

A comprehensive Spring Boot-based e-commerce platform template with microservice architecture. This project provides a robust foundation for building scalable online shopping applications, incorporating industry-standard practices and modern technologies.

## ✨ Key Features

- 🏗️ **Microservice Architecture** - Built with Spring Cloud Alibaba
- 🔐 **Security System** - JWT and OAuth2 integration
- 📦 **Data Management** - JPA and MyBatis support
- 💾 **Caching Solution** - Redis integration
- 📨 **Message Queue** - RabbitMQ implementation
- 🔄 **Gateway** - Spring Cloud Gateway
- ⚙️ **Service Discovery** - Spring Cloud Eureka
- 🤖 **AI Integration** - Ready for AI feature development
- ⏰ **Task Scheduling** - Quartz implementation
- 📧 **Email Service** - Spring Mail support

## 🛠️ Tech Stack

<div align="center">
  <table>
    <tr>
      <td align="center" width="96">
        <img src="https://cdn.simpleicons.org/spring/6DB33F" width="48" height="48" alt="Spring" />
        <br>Spring Boot
      </td>
      <td align="center" width="96">
        <img src="https://cdn.simpleicons.org/mysql/4479A1" width="48" height="48" alt="MySQL" />
        <br>MySQL
      </td>
      <td align="center" width="96">
        <img src="https://cdn.simpleicons.org/redis/DC382D" width="48" height="48" alt="Redis" />
        <br>Redis
      </td>
      <td align="center" width="96">
        <img src="https://cdn.simpleicons.org/rabbitmq/FF6600" width="48" height="48" alt="RabbitMQ" />
        <br>RabbitMQ
      </td>
      <td align="center" width="96">
        <img src="https://cdn.simpleicons.org/apachemaven/C71A36" width="48" height="48" alt="Maven" />
        <br>Maven
      </td>
    </tr>
  </table>
</div>

## 📚 Table of Contents

- [Prerequisites](#prerequisites)
- [Project Creation Guide](#project-creation-guide)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Common Issues](#common-issues)
- [Contributing](#contributing)
- [License](#license)

## 🔧 Prerequisites

> [!IMPORTANT]
> Before you begin, ensure you have the following installed:
> - JDK 17 or later
> - Maven 3.6+
> - MySQL 5.7+
> - IntelliJ IDEA (Recommended)
> - Git

## 🚀 Project Creation Guide

### Step 1: Project Setup

<details>
<summary>Create Project Using IntelliJ IDEA</summary>

1. Open IntelliJ IDEA
2. Click "New Project"
3. Select "Spring Initializr"
4. Configure project metadata:
   ```properties
   Group: com.douyinmall
   Artifact: douyin-mall-java-template
   Name: douyin-mall-java-template
   Description: Douyin Mall Java Template Project
   Package name: com.douyinmall.mall
   Packaging: Jar
   Java version: 17
   ```
   </details>

<details>
<summary>Select Dependencies</summary>

#### Core Dependencies
- Spring Web
- Spring Boot DevTools
- Lombok
- Spring Configuration Processor

#### Data Access
- Spring Data JPA
- MySQL Driver
- Spring Data Redis
- MyBatis Framework

#### Security
- Spring Security
- OAuth2 Resource Server
- Spring Session

#### Messaging
- Spring for RabbitMQ

#### Cloud Dependencies
- Eureka Discovery Client
- Config Client
- Gateway
- Resilience4j

#### Others
- Spring Boot Actuator
- Validation
- Java Mail Sender
- Quartz Scheduler
</details>

### Step 2: Configuration

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

### Step 3: Database Setup

```sql
CREATE DATABASE douyin_mall CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

## 📂 Project Structure

```
📦douyin-mall-java-template
 ┣ 📂src
 ┃ ┣ 📂main
 ┃ ┃ ┣ 📂java
 ┃ ┃ ┃ ┗ 📂com
 ┃ ┃ ┃ ┃ ┗ 📂douyinmall
 ┃ ┃ ┃ ┃ ┃ ┗ 📂mall
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜DouyinMallJavaTemplateApplication.java
 ┃ ┃ ┗ 📂resources
 ┃ ┃ ┃ ┣ 📂static
 ┃ ┃ ┃ ┣ 📂templates
 ┃ ┃ ┃ ┗ 📜application.properties
 ┃ ┗ 📂test
 ┃ ┃ ┗ 📂java
 ┃ ┃ ┃ ┗ 📂com
 ┃ ┃ ┃ ┃ ┗ 📂douyinmall
 ┃ ┃ ┃ ┃ ┃ ┗ 📂mall
 ┃ ┃ ┃ ┃ ┃ ┃ ┗ 📜DouyinMallJavaTemplateApplicationTests.java
 ┣ 📂target
 ┃ ┣ 📂classes
 ┃ ┃ ┣ 📂com
 ┃ ┃ ┃ ┗ 📂douyinmall
 ┃ ┃ ┃ ┃ ┗ 📂mall
 ┃ ┃ ┃ ┃ ┃ ┗ 📜DouyinMallJavaTemplateApplication.class
 ┃ ┃ ┗ 📜application.properties
 ┃ ┣ 📂generated-sources
 ┃ ┃ ┗ 📂annotations
 ┃ ┣ 📂generated-test-sources
 ┃ ┃ ┗ 📂test-annotations
 ┃ ┗ 📂test-classes
 ┃ ┃ ┗ 📂com
 ┃ ┃ ┃ ┗ 📂douyinmall
 ┃ ┃ ┃ ┃ ┗ 📂mall
 ┃ ┃ ┃ ┃ ┃ ┗ 📜DouyinMallJavaTemplateApplicationTests.class
 ┣ 📜.gitattributes
 ┣ 📜.gitignore
 ┣ 📜CODE_OF_CONDUCT.md
 ┣ 📜HELP.md
 ┣ 📜LICENSE
 ┣ 📜mvnw
 ┣ 📜mvnw.cmd
 ┣ 📜pom.xml
 ┗ 📜README.md
```

## 🚀 Running the Application

### Using Maven

```bash
# Build the project
mvn clean package

# Run the application
java -jar target/douyin-mall-java-template-0.0.1-SNAPSHOT.jar
```

### Using IDE
Run the main class `DouyinMallApplication.java` directly in your IDE.

## ❗ Common Issues

### JDK Version Mismatch
> [!TIP]
> If you encounter JDK version issues:
> - Verify JDK 17 installation
> - Check project structure settings
> - Confirm Maven compiler settings

### Database Connection
> [!NOTE]
> Common database connection issues:
> - MySQL service status
> - Database credentials
> - Database existence
> - Port availability

### Port Conflicts
If port 8080 is occupied, modify `server.port` in application.properties.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the Apache-2.0 License - see the LICENSE.md file for details.

## 🙋‍♀ Author

**Chan Meng**
- <img src="https://cdn.simpleicons.org/linkedin/0A66C2" width="16" height="16"> LinkedIn: [chanmeng666](https://www.linkedin.com/in/chanmeng666/)
- <img src="https://cdn.simpleicons.org/github/181717" width="16" height="16"> GitHub: [ChanMeng666](https://github.com/ChanMeng666)

---

<div align="center">
Made with ❤️ for Java developers
<br/>
⭐ Star us on GitHub | 📖 Read our Docs | 🐛 Report Issues
</div>
