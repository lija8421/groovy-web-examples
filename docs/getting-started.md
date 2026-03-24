# Getting Started with Groovy Web Examples

Welcome to Groovy Web Examples! This guide will help you set up your environment and start exploring the examples.

## Prerequisites

Before you begin, ensure you have the following installed:

### Required Software

- **Java Development Kit (JDK)**: Version 8 or higher
  - Download from [Oracle JDK](https://www.oracle.com/java/technologies/downloads/) or [OpenJDK](https://openjdk.org/)

- **Groovy**: Version 3.0 or higher
  ```bash
  # Using SDKMAN (recommended)
  sdk install groovy 3.0.10

  # Or download from https://groovy.apache.org/download.html
  ```

- **Gradle**: Version 6.0 or higher
  ```bash
  # Using SDKMAN
  sdk install gradle 7.4

  # Or download from https://gradle.org/install/
  ```

### Optional but Recommended

- **IDE**: IntelliJ IDEA (recommended), Eclipse, or VS Code
- **Git**: For version control
- **Postman** or **cURL**: For API testing

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/groovy-web/groovy-web-examples.git
cd groovy-web-examples
```

### 2. Verify Your Installation

```bash
# Check Java version
java -version

# Check Groovy version
groovy -version

# Check Gradle version
gradle -version
```

### 3. Build the Project

```bash
./gradlew build
```

## Running Examples

Each example is self-contained and can be run independently.

### Grails Examples

```bash
cd examples/grails/basic-crud
./gradlew bootRun
```

The application will be available at `http://localhost:8080`

### Ratpack Examples

```bash
cd examples/ratpack/hello-world
./gradlew run
```

Access at `http://localhost:5050`

### Micronaut Examples

```bash
cd examples/micronaut/microservice
./gradlew run
```

Available at `http://localhost:8080`

## Project Structure

Understanding the repository structure:

```
groovy-web-examples/
├── docs/                           # Documentation
│   ├── getting-started.md         # This file
│   ├── frameworks.md              # Framework comparisons
│   └── best-practices.md          # Coding standards
├── examples/                       # Example code
│   ├── grails/                    # Grails framework examples
│   │   ├── basic-crud/           # CRUD operations
│   │   ├── rest-api/             # RESTful APIs
│   │   └── security/             # Authentication/authorization
│   ├── ratpack/                   # Ratpack framework examples
│   │   ├── async-handlers/       # Async processing
│   │   └── streaming/            # Real-time streaming
│   ├── micronaut/                 # Micronaut framework examples
│   │   ├── microservices/        # Microservice architecture
│   │   └── graalvm/              # Native images
│   └── testing/                   # Testing examples
│       ├── spock/                # Specification testing
│       └── geb/                  # Functional testing
└── README.md                       # Repository overview
```

## Next Steps

### Choose Your Path

1. **New to Groovy Web Development?**
   - Start with [Grails Basic CRUD](../examples/grails/basic-crud/)
   - Learn [REST API fundamentals](../examples/grails/rest-api/)

2. **Interested in Async Programming?**
   - Explore [Ratpack Async Handlers](../examples/ratpack/async-handlers/)
   - Try [Streaming Examples](../examples/ratpack/streaming/)

3. **Building Microservices?**
   - Check out [Micronaut Microservices](../examples/micronaut/microservices/)
   - Learn about [GraalVM Native Images](../examples/micronaut/graalvm/)

4. **Focus on Testing?**
   - Start with [Spock Framework](../examples/testing/spock/)
   - Try [Geb Functional Testing](../examples/testing/geb/)

### Learn More

- [Framework Comparisons](frameworks.md) - Choose the right framework
- [Best Practices](best-practices.md) - Write better code
- [Groovy Documentation](https://groovy.apache.org/docs.html)
- [Grails Guides](https://guides.grails.org/)

## Common Tasks

### Running Tests

```bash
# Run all tests
./gradlew test

# Run tests for a specific example
cd examples/grails/basic-crud
./gradlew test

# Run with coverage
./gradlew test jacocoTestReport
```

### Cleaning Build Artifacts

```bash
./gradlew clean
```

### Generating Documentation

```bash
./gradlew groovydoc
```

Output will be in `build/docs/groovydoc/`

## Troubleshooting

### Port Already in Use

If you get a "port already in use" error:

```bash
# Find the process using the port (example: port 8080)
lsof -i :8080

# Kill the process
kill -9 <PID>
```

### Gradle Daemon Issues

```bash
# Stop the Gradle daemon
./gradlew --stop

# Then try your command again
./gradlew build
```

### Memory Issues

Increase memory allocation:

```bash
# In gradle.properties
org.gradle.jvmargs=-Xmx2048m -XX:MaxPermSize=512m
```

## IDE Setup

### IntelliJ IDEA

1. Open the project folder
2. Let IntelliJ auto-detect Gradle
3. Wait for dependency resolution
4. Right-click on an example's `Application.groovy` and select "Run"

### VS Code

1. Install the "Groovy Lint" extension
2. Install the "Gradle for Java" extension
3. Open the project folder
4. Use the integrated terminal to run examples

### Eclipse

1. Generate Eclipse project files:
   ```bash
   ./gradlew eclipse
   ```
2. Import as "Existing Gradle Project"
3. Select the project folder

## Getting Help

If you encounter issues:

1. Check the [Troubleshooting section](#troubleshooting)
2. Search [existing GitHub issues](https://github.com/groovy-web/groovy-web-examples/issues)
3. Create a [new issue](https://github.com/groovy-web/groovy-web-examples/issues/new)
4. Join our community discussions

## Contributing

We welcome contributions! See [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines.

Happy coding!
