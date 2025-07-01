# jslovers-backend

A Spring Boot API backend for the jslovers community. This project follows open source and team development best practices.

## Features
- Spring Boot 3.x (Java 21+)
- OpenAPI documentation (`api.yml`)
- Dockerized for easy deployment
- Standardized project structure and contribution guidelines

## Getting Started

### Prerequisites
- Java 21+
- Maven 3.8+
- Docker (optional, for containerization)

### Local Development

#### MongoDB Connection
This project uses MongoDB as its database. The connection URI is supplied via the environment variable `SPRING_DATA_MONGODB_URI`. You must set this variable in your environment, regardless of how you run the project (Docker, local, CI, etc.).

- **Docker Compose:** The variable is set in `docker-compose.yml`.
- **Local/IDE:** Set it in your shell before running:
  ```sh
  export SPRING_DATA_MONGODB_URI=mongodb://localhost:27017/jslovers
  mvn spring-boot:run
  ```
- **.env file:** You can also use a `.env` file if your tooling supports it.

#### Run with Maven
```
mvn spring-boot:run
```

#### Run with Docker
Build the JAR:
```
mvn clean package -DskipTests
```
Build and run the container:
```
docker build -t jslovers-backend .
docker run -p 8080:8080 --env-file .env jslovers-backend
```
Or use Docker Compose:
```
docker-compose up --build
```

> **Note:**
> If you see an error like `failed to solve: lstat /target: no such file or directory`, make sure you have built the JAR file first using the Maven command above. The Docker build expects `target/*.jar` to exist.

The api will be running at: http://localhost:8080/swagger-ui/index.html

### Environment Variables
See `.env.example` for required/optional environment variables.

## API Documentation

After starting the backend, you can access the interactive Swagger UI here:

- [Swagger UI](http://localhost:8080/swagger-ui.html)

The OpenAPI spec (JSON) is available at:
- [OpenAPI JSON](http://localhost:8080/v3/api-docs)

## Contributing
See [`CONTRIBUTING.md`](CONTRIBUTING.md) for guidelines.

## Code of Conduct
See [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md).

## Security
See [`SECURITY.md`](SECURITY.md) for vulnerability reporting.

## License
MIT License. See [`LICENSE`](LICENSE).

## Changelog
See [`CHANGELOG.md`](CHANGELOG.md).
