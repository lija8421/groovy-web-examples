# Groovy Web Examples

[![Built by Groovy Web](https://img.shields.io/badge/Built%20by-Groovy%20Web-0f3460?logo=github&logoColor=white)](https://www.groovyweb.co/?utm_source=github&utm_medium=readme&utm_campaign=groovy-examples)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A comprehensive collection of examples, tutorials, and best practices for building modern web applications with Groovy.

## Overview

This repository contains practical examples demonstrating Groovy's power in web development, including:
- Web framework integrations (Grails, Ratpack, Micronaut)
- RESTful API development
- Database integration (GORM, JDBC)
- Testing strategies
- Deployment configurations

## Quick Start

```bash
# Clone the repository
git clone https://github.com/groovy-web/groovy-web-examples.git
cd groovy-web-examples

# Explore examples by category
ls examples/
```

## Repository Structure

```
groovy-web-examples/
├── docs/                    # Detailed documentation
│   ├── getting-started.md
│   ├── frameworks.md
│   └── best-practices.md
├── examples/                # Code examples
│   ├── grails/
│   ├── ratpack/
│   ├── micronaut/
│   └── testing/
├── .github/                 # GitHub templates
└── README.md
```

## Examples by Category

### Grails Framework
- **Basic CRUD**: Simple create-read-update-delete operations
- **REST APIs**: Building RESTful services
- **Domain Modeling**: GORM relationships and validation
- **Security**: Authentication and authorization

### Ratpack
- **Async Handlers**: Non-blocking request handling
- **Streaming**: Real-time data streaming
- **Routing**: Advanced routing patterns

### Micronaut
- **Microservices**: Building cloud-native applications
- **GraalVM**: Native image compilation
- **Reactive Programming**: Non-blocking I/O

### Testing
- **Spock Framework**: Specification-based testing
- **Geb**: Functional web testing
- **Integration Tests**: End-to-end testing strategies

## Documentation

- [Getting Started](docs/getting-started.md) - Setup and installation
- [Framework Guides](docs/frameworks.md) - Detailed framework comparisons
- [Best Practices](docs/best-practices.md) - Coding standards and patterns

## Requirements

- Java 8 or higher
- Groovy 3.0+
- Gradle 6.0+ (for building examples)

## Running Examples

Each example includes its own README with specific instructions:

```bash
cd examples/grails/basic-crud
./gradlew bootRun
```

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

## Code of Conduct

Please read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) to understand our community standards.

## Support

- GitHub Issues: Report bugs and request features
- Discussions: Ask questions and share ideas
- Wiki: Additional documentation and tutorials

## Resources

- [Apache Groovy](https://groovy.apache.org/)
- [Grails Framework](https://grails.org/)
- [Ratpack](https://ratpack.io/)
- [Micronaut](https://micronaut.io/)

---

## Related Repositories

Explore more open-source tools from [Groovy Web](https://www.groovyweb.co/?utm_source=github&utm_medium=readme&utm_campaign=cross-link):

- **[langchain-multi-agent-example](https://github.com/groovy-web/langchain-multi-agent-example)** -- Multi-agent systems tutorial with LangChain
- **[rag-system-pgvector](https://github.com/groovy-web/rag-system-pgvector)** -- Production RAG with PostgreSQL + pgvector
- **[rag-systems-production](https://github.com/groovy-web/rag-systems-production)** -- Enterprise-grade RAG systems
- **[ai-testing-mcp](https://github.com/groovy-web/ai-testing-mcp)** -- AI testing via Model Context Protocol
- **[edge-computing-starter](https://github.com/groovy-web/edge-computing-starter)** -- Cloudflare Workers + Hono template
- **[claude-code-workflows](https://github.com/groovy-web/claude-code-workflows)** -- Workflows for Claude Code
- **[groovy-web-ai-agents](https://github.com/groovy-web/groovy-web-ai-agents)** -- Production AI agent configs
- **[groovy-web-examples](https://github.com/groovy-web/groovy-web-examples)** -- Groovy/Grails examples
