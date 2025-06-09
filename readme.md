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

#### Run with Maven
```
cd backend
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

### Environment Variables
See `.env.example` for required/optional environment variables.

## API Documentation
- OpenAPI spec: [`api.yml`](api.yml)

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
