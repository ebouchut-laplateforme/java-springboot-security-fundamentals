Scaffolds a conventional Spring Boot 3.5.8 application with Java 17, including test coverage, database connectivity, security, and template engine support.
The project is structured as a reusable template with `.keepme` files in all empty directories.

## Project Configuration

- **Build**: Maven with Spring Boot parent POM 3.5.8
- **Java**: 17 (configured via `java.version` property only)
- **SDKMAN**: `.sdkmanrc` configures Java `17.0.17-tem` and Maven 3.9.11
- **GAV**: `com.ericbouchut.java.springboot:springboot-ecf1:0.0.1-SNAPSHOT`

## Dependencies

- **Testing**: JUnit 5 (5.9.2), JaCoCo (0.8.10), Surefire (3.0.0)
- **Security**: Spring Security 6.5.7 with default configuration
- **Data**: Spring Data JPA, MySQL Connector J 8.4.0
- **View**: Thymeleaf with Spring integration
- **API Documentation**: SpringDoc OpenAPI 2.2.0 (Swagger UI)
- **Utilities**: Lombok with annotation processor enabled

## Structure

```
src/
├── main/
│   ├── java/com/ericbouchut/java/springboot/ecf1/
│   │   ├── Application.java          # @SpringBootApplication entry point
│   │   ├── controller/               # REST/MVC controllers (.keepme)
│   │   ├── service/                  # Business logic layer (.keepme)
│   │   ├── repository/               # Data access layer (.keepme)
│   │   ├── model/                    # Domain entities (.keepme)
│   │   ├── dto/                      # Data Transfer Objects (.keepme)
│   │   ├── config/                   # Configuration classes (.keepme)
│   │   ├── exception/                # Custom exceptions (.keepme)
│   │   └── util/                     # Utility classes (.keepme)
│   └── resources/
│       ├── application.yaml           # MySQL on port 3384, JPA/Thymeleaf config
│       ├── static/                    # Static assets (.keepme)
│       └── templates/                 # Thymeleaf templates (.keepme)
└── test/
    └── java/com/ericbouchut/java/springboot/ecf1/
        └── ApplicationTests.java      # Context load test
```

The project follows the most common Spring Boot naming conventions using singular package names (controller, service, repository, model, dto, config, exception, util). All empty directories contain `.keepme` files to ensure they are tracked in version control, making this repository suitable for use as a project template.

## Database Configuration

MySQL connection configured for local development on non-standard port:

```yaml
spring:
  application:
    name: springboot-ecf1
  datasource:
    url: jdbc:mysql://localhost:3384/ecf1_db?useSSL=false&serverTimezone=UTC
    username: root
    password: 
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
```

