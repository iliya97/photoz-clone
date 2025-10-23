# PhotoZ Clone 📸

A RESTful API application built with Spring Boot for managing photo records. This project demonstrates fundamental Spring Boot concepts including REST controllers, data models, and HTTP request handling.

## 🚀 Quick Start

```bash
# Clone the repository
git clone <your-repo-url>

# Navigate to project directory
cd photoz-clone

# Run the application
./mvnw spring-boot:run

# Test the API
curl http://localhost:8080/photoz
```

## 📋 Overview

PhotoZ Clone is a lightweight Spring Boot application that provides basic CRUD operations for photo management through a RESTful API. It uses an in-memory data store to manage photo records with unique IDs and filenames.

### Key Features
- ✅ RESTful API endpoints
- ✅ CORS enabled for cross-origin requests
- ✅ Simple in-memory data storage
- ✅ Clean MVC architecture
- ✅ JSON response format
- ✅ Input validation with Jakarta Bean Validation
- ✅ Auto-generated unique IDs (UUID)
- ✅ Error handling with proper HTTP status codes

## 🛠️ Technology Stack

- **Java 25**
- **Spring Boot 3.5.6**
- **Spring Web** - RESTful web services
- **Spring Boot Validation** - Request validation with Jakarta Bean Validation
- **Spring Data JDBC** - Database connectivity
- **H2 Database** - In-memory database (configured)
- **Maven** - Build and dependency management

## 📁 Project Structure

```
photoz-clone/
├── src/main/java/com/jetbrains/deng/photoz/clone/
│   ├── Photo.java                    # Data model
│   ├── PhotozCloneApplication.java   # Main application class
│   └── PhotozController.java         # REST API controller
├── src/main/resources/
│   └── application.properties        # Configuration file
├── pom.xml                           # Maven dependencies
└── README.md                         # This file
```

## 🌐 API Endpoints

| Method | Endpoint | Description | Response |
|--------|----------|-------------|----------|
| `GET` | `/` | Health check | "hello world" |
| `GET` | `/photoz` | Get all photos | Array of photos |
| `GET` | `/photoz/{id}` | Get photo by ID | Single photo object |
| `POST` | `/photoz` | Create new photo | Created photo object with UUID |
| `DELETE` | `/photoz/{id}` | Delete photo by ID | 200 OK or 404 Not Found |

### Example Requests

**Get all photos:**
```bash
curl http://localhost:8080/photoz
```

**Get specific photo:**
```bash
curl http://localhost:8080/photoz/1
```

**Create photo:**
```bash
curl -X POST http://localhost:8080/photoz \
  -H "Content-Type: application/json" \
  -d '{"fileName": "sunset.jpg"}'
```

**Delete photo:**
```bash
curl -X DELETE http://localhost:8080/photoz/1
```

### Example Response

**GET /photoz:**
```json
[
  {
    "id": "550e8400-e29b-41d4-a716-446655440000",
    "fileName": "hello.jpg"
  }
]
```

**POST /photoz:**
```json
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "fileName": "sunset.jpg"
}
```

## 💻 Installation & Setup

### Prerequisites
- Java 25 JDK
- Maven 3.6+ (or use included Maven wrapper)

### Steps

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd photoz-clone
   ```

2. **Build the project**
   ```bash
   ./mvnw clean install
   ```

3. **Run the application**
   ```bash
   ./mvnw spring-boot:run
   ```
   
   Or run the JAR directly:
   ```bash
   java -jar target/photoz-clone-0.0.1-SNAPSHOT.jar
   ```

4. **Access the application**
   - Base URL: `http://localhost:8080`
   - API endpoint: `http://localhost:8080/photoz`

## ⚙️ Configuration

The application runs on port 8080 by default. To change the port, edit `src/main/resources/application.properties`:

```properties
server.port=8081
```

## 📚 Documentation

For detailed documentation including code explanations, design patterns, and future enhancements, see [DOCUMENTATION.md](DOCUMENTATION.md).

## 🧪 Testing

Run the test suite:
```bash
./mvnw test
```

## 🔧 Development

### Project Components

1. **Photo.java** - POJO representing a photo entity with validation annotations
   - `@NotEmpty` validation on `fileName` field
2. **PhotozController.java** - REST controller handling HTTP requests
   - `@Valid` annotation for request body validation
   - UUID generation for new photo IDs
3. **PhotozCloneApplication.java** - Spring Boot application entry point

### Data Storage
Currently uses an in-memory HashMap. Data is not persisted between restarts.

## 🚧 Future Enhancements

- [x] Add POST endpoint for creating new photos
- [x] Add input validation
- [ ] Add PUT endpoint for updating photos
- [ ] Integrate persistent database (PostgreSQL/MySQL)
- [ ] Add file upload functionality
- [ ] Implement authentication/authorization
- [ ] Add more comprehensive validation (file format, size, etc.)
- [ ] Add Swagger/OpenAPI documentation
- [ ] Implement comprehensive unit tests
- [ ] Add logging and monitoring

## 🐛 Troubleshooting

**Port already in use:**
- Change the port in `application.properties`
- Or kill the process using port 8080

**Build failures:**
```bash
./mvnw clean install -U
```

**Java version issues:**
Ensure Java 25 is installed:
```bash
java -version
```

## 📝 License

This is a demo project for learning purposes.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 📧 Contact

For questions or feedback, please open an issue in the repository.

---

**Built with ❤️ using Spring Boot**
