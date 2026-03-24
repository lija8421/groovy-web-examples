# Hello World - Grails Example

A simple "Hello World" web application using Grails framework.

## Overview

This example demonstrates the basic structure of a Grails application with a simple controller that returns "Hello World!".

## Prerequisites

- Java 8 or higher
- Grails 5.0+
- Gradle (included with Grails)

## Project Structure

```
hello-world/
├── grails-app/
│   ├── controllers/
│   │   └── example/
│   │       └── HelloWorldController.groovy
│   ├── views/
│   │   └── helloWorld/
│   │       └── index.gsp
│   └── init/
│       └── example/
│           └── BootStrap.groovy
├── build.gradle
└── README.md
```

## Running the Application

### Using Gradle

```bash
./gradlew bootRun
```

### Using Grails Command

```bash
grails run-app
```

The application will be available at: `http://localhost:8080`

## Accessing the Application

### Browser

Open your browser and navigate to:
```
http://localhost:8080/helloWorld
```

### cURL

```bash
curl http://localhost:8080/helloWorld
```

### Response

You should see:
```
Hello World!
```

## Code Overview

### Controller

**File**: `grails-app/controllers/example/HelloWorldController.groovy`

```groovy
package example

class HelloWorldController {

    def index() {
        render "Hello World!"
    }
}
```

### Explanation

- **Package**: `example` - Organizes controllers
- **Class**: `HelloWorldController` - Controller class
- **Action**: `index()` - Default action
- **Response**: `render "Hello World!"` - Renders text response

## Customization

### Change the Message

Edit `HelloWorldController.groovy`:

```groovy
def index() {
    render "Hello from Grails!"
}
```

### Add HTML Response

```groovy
def index() {
    render """
    <html>
        <body>
            <h1>Hello World!</h1>
            <p>Welcome to Grails</p>
        </body>
    </html>
    """
}
```

### Add Parameters

```groovy
def index() {
    def name = params.name ?: "World"
    render "Hello ${name}!"
}
```

Access with: `http://localhost:8080/helloWorld?name=John`

## Testing

### Run Tests

```bash
./gradlew test
```

### Test Location

`src/test/groovy/example/HelloWorldControllerSpec.groovy`

### Test Code

```groovy
package example

import grails.testing.web.controllers.ControllerUnitTest
import spock.lang.Specification

class HelloWorldControllerSpec extends Specification
        implements ControllerUnitTest<HelloWorldController> {

    void "test index action"() {
        when: "index is called"
        controller.index()

        then: "response is Hello World!"
        response.text == "Hello World!"
    }
}
```

## Next Steps

1. Add a view (GSP template)
2. Create a domain class
3. Add database persistence
4. Create a service

## Related Examples

- [Basic CRUD](../basic-crud/) - Create, read, update, delete operations
- [REST API](../rest-api/) - Building RESTful APIs
- [Database Integration](../database/) - Working with GORM

## Resources

- [Grails Documentation](https://docs.grails.org/)
- [Grails Guides](https://guides.grails.org/)
- [Groovy Documentation](https://groovy.apache.org/docs.html)

## Troubleshooting

### Port Already in Use

If port 8080 is already in use:

```bash
# Find process using port 8080
lsof -i :8080

# Kill the process
kill -9 <PID>

# Or use different port
grails run-app -port 8081
```

### Build Fails

```bash
# Clean build
./gradlew clean build

# Remove cache
./gradlew cleanBuildCache
```

## License

This example is part of Groovy Web Examples and is licensed under the MIT License.
