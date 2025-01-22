<div align="center">
 <h1>🛍️ 抖音商城 Java 模板<br/><small>一个生产级电商平台</small></h1>
 <img src="https://img.shields.io/badge/spring%20boot-3.4.1-brightgreen.svg"/>
 <img src="https://img.shields.io/badge/JDK-17-blue.svg"/>
 <img src="https://img.shields.io/badge/maven-3.6%2B-important.svg"/>
 <img src="https://img.shields.io/badge/mysql-5.7%2B-blue.svg"/>
 <img src="https://img.shields.io/badge/redis-6.0%2B-red.svg"/>
</div>

> [!IMPORTANT]
> 这是一个基于 Spring Boot 和微服务架构构建的生产级模板项目。虽然它展示了行业最佳实践，但在部署到生产环境之前，请务必全面审查和加强安全措施。

[English](README.md) | [简体中文](README.zh-CN.md)

# 🌟 简介

这是一个基于 Spring Boot 的综合性电商平台模板，采用微服务架构。该项目为构建可扩展的在线购物应用程序提供了强大的基础，整合了行业标准实践和现代技术。

## ✨ 核心特性

- 🏗️ **微服务架构** - 基于 Spring Cloud Alibaba 构建
- 🔐 **安全系统** - JWT 和 OAuth2 集成
- 📦 **数据管理** - 支持 JPA 和 MyBatis
- 💾 **缓存方案** - Redis 集成
- 📨 **消息队列** - RabbitMQ 实现
- 🔄 **网关** - Spring Cloud Gateway
- ⚙️ **服务发现** - Spring Cloud Eureka
- 🤖 **AI 集成** - 已具备 AI 功能开发准备
- ⏰ **任务调度** - Quartz 实现
- 📧 **邮件服务** - Spring Mail 支持

## 🛠️ 技术栈

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

## 📚 目录

- [环境要求](#-环境要求)
- [项目创建指南](#-项目创建指南)
- [项目结构](#-项目结构)
- [配置说明](#-配置说明)
- [运行应用](#-运行应用)
- [常见问题](#-常见问题)
- [贡献指南](#-贡献指南)
- [许可证](#-许可证)

## 🔧 环境要求

> [!IMPORTANT]
> 开始之前，请确保已安装以下软件：
> - JDK 17 或更高版本
> - Maven 3.6+
> - MySQL 5.7+
> - IntelliJ IDEA (推荐)
> - Git

## 🚀 项目创建指南

### 步骤 1：项目设置

<details>
<summary>使用 IntelliJ IDEA 创建项目</summary>

1. 打开 IntelliJ IDEA
2. 点击"新建项目"
3. 选择"Spring Initializr"
4. 配置项目元数据：
   ```properties
   Group: com.douyinmall
   Artifact: douyin-mall-java-template
   Name: douyin-mall-java-template
   Description: 抖音商城 Java 模板项目
   Package name: com.douyinmall.mall
   Packaging: Jar
   Java version: 17
   ```
   </details>

<details>
<summary>选择依赖</summary>

#### 核心依赖
- Spring Web
- Spring Boot DevTools
- Lombok
- Spring Configuration Processor

#### 数据访问
- Spring Data JPA
- MySQL Driver
- Spring Data Redis
- MyBatis Framework

#### 安全
- Spring Security
- OAuth2 Resource Server
- Spring Session

#### 消息
- Spring for RabbitMQ

#### 云服务依赖
- Eureka Discovery Client
- Config Client
- Gateway
- Resilience4j

#### 其他
- Spring Boot Actuator
- Validation
- Java Mail Sender
- Quartz Scheduler
</details>

### 步骤 2：配置

在 `src/main/resources` 中创建 `application.properties`：

```properties
# 应用
spring.application.name=douyin-mall
server.port=8080

# 数据库
spring.datasource.url=jdbc:mysql://localhost:3306/douyin_mall?useUnicode=true&characterEncoding=utf8&serverTimezone=Asia/Shanghai
spring.datasource.username=root
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA
spring.jpa.database-platform=org.hibernate.dialect.MySQLDialect
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update
spring.jpa.open-in-view=false

# 初始禁用服务
spring.autoconfigure.exclude=\
  org.springframework.boot.autoconfigure.data.redis.RedisAutoConfiguration,\
  org.springframework.boot.autoconfigure.data.redis.RedisRepositoriesAutoConfiguration,\
  org.springframework.boot.autoconfigure.amqp.RabbitAutoConfiguration

# Eureka Client
eureka.client.enabled=false
```

### 步骤 3：数据库设置

```sql
CREATE DATABASE douyin_mall CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

## 📂 项目结构

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
 ┃ ┣ 📂generated-sources
 ┃ ┣ 📂generated-test-sources
 ┃ ┗ 📂test-classes
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

## 🚀 运行应用

### 使用 Maven

```bash
# 构建项目
mvn clean package

# 运行应用
java -jar target/douyin-mall-java-template-0.0.1-SNAPSHOT.jar
```

### 使用 IDE
直接在 IDE 中运行主类 `DouyinMallApplication.java`。

## ❗ 常见问题

### JDK 版本不匹配
> [!TIP]
> 如果遇到 JDK 版本问题：
> - 验证 JDK 17 安装情况
> - 检查项目结构设置
> - 确认 Maven 编译器设置

### 数据库连接
> [!NOTE]
> 常见数据库连接问题：
> - MySQL 服务状态
> - 数据库凭证
> - 数据库是否存在
> - 端口可用性

### 端口冲突
如果端口 8080 被占用，请修改 application.properties 中的 `server.port`。

## 🤝 贡献指南

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m '添加一些功能'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

## 📄 许可证

本项目采用 Apache-2.0 许可证 - 详见 LICENSE.md 文件。

## 🙋‍♀ 作者

**Chan Meng**
- <img src="https://cdn.simpleicons.org/linkedin/0A66C2" width="16" height="16"> LinkedIn: [chanmeng666](https://www.linkedin.com/in/chanmeng666/)
- <img src="https://cdn.simpleicons.org/github/181717" width="16" height="16"> GitHub: [ChanMeng666](https://github.com/ChanMeng666)

---

<div align="center">
用 ❤️ 为 Java 开发者打造
<br/>
⭐ 在 GitHub 上为我们点星 | 📖 阅读文档 | 🐛 报告问题
</div>