# Framework Comparison Guide

This guide compares the three main Groovy web frameworks: Grails, Ratpack, and Micronaut, helping you choose the right one for your project.

## Overview

| Feature | Grails | Ratpack | Micronaut |
|---------|--------|---------|-----------|
| **Type** | Full-stack Framework | Lightweight Toolkit | Cloud-Native Framework |
| **Learning Curve** | Easy | Medium | Medium |
| **Startup Time** | Slow | Fast | Very Fast |
| **Memory Footprint** | High | Low | Low |
| **Best For** | Rapid development | Async applications | Microservices, serverless |

## Grails

### Overview

Grails is a full-stack web application framework built on top of Spring Boot and Hibernate. It follows the "Convention over Configuration" philosophy, inspired by Ruby on Rails.

### Strengths

- **Rapid Development**: Scaffolding and code generation
- **Rich Ecosystem**: Hundreds of plugins
- **GORM**: Powerful ORM for database access
- **Mature**: Battle-tested since 2008
- **Easy to Learn**: Great for beginners

### Weaknesses

- **Heavy**: Larger memory footprint
- **Slower Startup**: Due to heavy initialization
- **Monolithic**: Not ideal for microservices

### When to Use Grails

- Building traditional web applications
- Need rapid prototyping
- Team is new to Groovy
- Require a full-featured framework
- Building CRUD applications

### Code Example

```groovy
class UserController {
    def index() {
        respond User.list()
    }

    def show(Long id) {
        respond User.get(id)
    }

    def save(User user) {
        if (user.save()) {
            respond user, status: CREATED
        } else {
            respond user.errors, status: NOT_ACCEPTABLE
        }
    }
}
```

## Ratpack

### Overview

Ratpack is a lightweight, non-blocking web toolkit built on Netty. It's designed for asynchronous, event-driven applications.

### Strengths

- **Non-Blocking**: Excellent async support
- **Fast**: Minimal overhead
- **Composable**: Functional programming model
- **Modular**: Use only what you need
- **Flexible**: Not opinionated

### Weaknesses

- **Steeper Learning Curve**: Async programming model
- **Less Opinionated**: More decisions to make
- **Fewer Conventions**: More configuration needed
- **Smaller Ecosystem**: Fewer plugins than Grails

### When to Use Ratpack

- Building async APIs
- Need high performance
- Building microservices
- Want functional programming
- Require real-time features

### Code Example

```groovy
class UserHandlers {
    final UserService userService

    void list(Context context) {
        context.render(json(userService.list()))
    }

    void get(Context context) {
        def id = context.pathTokens.id as Long
        context.render(json(userService.get(id)))
    }
}

// Routing
ratpack {
    handlers {
        get('users', new UserHandlers()::list)
        get('users/:id', new UserHandlers()::get)
    }
}
```

## Micronaut

### Overview

Micronaut is a modern, JVM-based framework for building cloud-native microservices and serverless applications. It uses compile-time dependency injection.

### Strengths

- **Fast Startup**: Compile-time DI, no reflection
- **Low Memory**: Minimal memory footprint
- **Cloud-Native**: Built for containers and Kubernetes
- **Reactive**: Supports reactive programming
- **Modern**: Latest Java/Groovy features

### Weaknesses

- **Younger**: Less mature than Grails
- **Smaller Community**: But growing fast
- **Different Paradigm**: Compile-time vs runtime
- **Learning Curve**: New concepts to learn

### When to Use Micronaut

- Building microservices
- Deploying to Kubernetes
- Serverless functions
- Need fast startup
- Building cloud-native applications

### Code Example

```groovy
@Controller('/users')
class UserController {
    final UserService userService

    @Get('/')
    List<User> list() {
        userService.list()
    }

    @Get('/{id}')
    User show(Long id) {
        userService.get(id)
    }

    @Post('/')
    User save(@Body User user) {
        userService.save(user)
    }
}
```

## Feature Comparison

### Database Access

| Framework | ORM Support | Migration Tools |
|-----------|-------------|-----------------|
| Grails | GORM (excellent) | Database migrations plugin |
| Ratpack | Manual | Use external tools |
| Micronaut | GORM, JDBC, R2DBC | Micronaut migrations, Flyway, Liquibase |

### Testing

| Framework | Unit Testing | Integration Testing |
|-----------|--------------|---------------------|
| Grails | Grails test support, Spock | Grails test mixins |
| Ratpack | Ratpack test support | Ratpack Groovy test |
| Micronaut | Micronaut test, Spock | Micronaut HTTP client |

### Dependency Injection

| Framework | DI Type |
|-----------|---------|
| Grails | Spring (runtime) |
| Ratpack | Manual registry |
| Micronaut | JSR-330 (compile-time) |

### Reactive Support

| Framework | Reactive | Non-Blocking |
|-----------|----------|--------------|
| Grails | Limited (via plugins) | Partial |
| Ratpack | Yes (Promise) | Yes |
| Micronaut | Yes (RxJava, Reactor) | Yes |

## Performance Comparison

### Startup Time (approximate)

- Grails: 8-15 seconds
- Ratpack: 1-2 seconds
- Micronaut: 1-2 seconds

### Memory Usage (approximate, idle)

- Grails: 300-500 MB
- Ratpack: 50-100 MB
- Micronaut: 50-100 MB

### Throughput (requests/second)

- Grails: 1,000-2,000
- Ratpack: 10,000-20,000
- Micronaut: 10,000-20,000

## Migration Paths

### From Grails to Micronaut

Micronaut supports GORM, making migration easier:

```groovy
// Micronaut with GORM
@Singleton
class UserService {
    @Inject
    Datastore datastore

    List<User> list() {
        User.findAll()
    }
}
```

### From Ratpack to Micronaut

Both are non-blocking, but concepts differ:

- Ratpack uses `Promise`
- Micronaut uses `Publisher` (Reactive Streams)

```groovy
// Ratpack
promise { fulfill ->
    fulfill(result)
}

// Micronaut
Flowable.just(result)
```

## Choosing the Right Framework

### Decision Tree

```
Need a full-featured framework?
├── Yes → Grails
└── No
    ├── Building microservices?
    │   ├── Yes → Micronaut
    │   └── No
    │       ├── Need async/event-driven?
    │       │   ├── Yes → Ratpack
    │       │   └── No → Grails
    └── Deploying to serverless?
        └── Yes → Micronaut
```

### Recommendations by Use Case

| Use Case | Recommended Framework |
|----------|---------------------|
| Traditional CRUD App | Grails |
| REST API | Any (Micronaut or Grails) |
| Microservices | Micronaut |
| Real-time Streaming | Ratpack |
| Serverless Functions | Micronaut |
| Rapid Prototyping | Grails |
| High-Performance API | Ratpack or Micronaut |
| Enterprise Application | Grails |

## Learning Path

### Beginner Path

1. Start with **Grails** for fundamentals
2. Learn GORM for database access
3. Explore Grails plugins
4. Build a complete CRUD application

### Advanced Path

1. Learn **Ratpack** for async programming
2. Understand functional composition
3. Build reactive APIs
4. Explore streaming applications

### Modern Path

1. Start with **Micronaut**
2. Learn compile-time DI
3. Build microservices
4. Deploy to Kubernetes

## Conclusion

All three frameworks are excellent choices. The right one depends on:

- **Project Requirements**: Microservices vs monolithic
- **Team Expertise**: Experience level
- **Performance Needs**: Startup time, memory, throughput
- **Deployment Target**: Traditional vs cloud-native

Our recommendation: **Start with what you know**, then explore other frameworks as needed.

## Resources

- [Grails Documentation](https://docs.grails.org/)
- [Ratpack Manual](https://ratpack.io/manual/)
- [Micronaut Guides](https://guides.micronaut.io/)
- [Framework Comparison Blog Post](https://example.com/blog)
