# Contributing to Groovy Web Examples

Thank you for your interest in contributing to Groovy Web Examples! This document provides guidelines and instructions for contributing.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Contributing Guidelines](#contributing-guidelines)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)

## Code of Conduct

Please read and follow our [Code of Conduct](CODE_OF_CONDUCT.md).

## Getting Started

### Prerequisites

- Java 8 or higher
- Groovy 3.0+
- Gradle 6.0+
- Git
- A GitHub account

### Setting Up Your Development Environment

1. **Fork the repository**

   ```bash
   # Fork the repo on GitHub, then clone your fork
   git clone https://github.com/groovy-web/groovy-web-examples.git
   cd groovy-web-examples
   ```

2. **Add upstream remote**

   ```bash
   git remote add upstream https://github.com/original-owner/groovy-web-examples.git
   ```

3. **Install dependencies**

   ```bash
   ./gradlew build
   ```

4. **Run tests**

   ```bash
   ./gradlew test
   ```

## Development Setup

### Creating a New Example

1. **Choose the appropriate category**

   - `grails/` - Grails framework examples
   - `ratpack/` - Ratpack framework examples
   - `micronaut/` - Micronaut framework examples
   - `testing/` - Testing examples

2. **Create the example directory**

   ```bash
   mkdir examples/grails/my-new-example
   cd examples/grails/my-new-example
   ```

3. **Add required files**

   - `README.md` - Example description and setup
   - `build.gradle` - Build configuration
   - `src/` - Source code
   - `tests/` - Test files

4. **Document your example**

   Create a comprehensive README with:
   - Purpose and description
   - Prerequisites
   - Setup instructions
   - Code explanation
   - Expected output

### Running Examples

```bash
cd examples/your-category/your-example
./gradlew run
```

## Contributing Guidelines

### What to Contribute

We welcome contributions in the following areas:

- **New Examples**: Add practical, well-documented examples
- **Bug Fixes**: Fix errors in existing examples
- **Documentation**: Improve READMEs and documentation
- **Tests**: Add or improve test coverage
- **Code Quality**: Refactor for clarity and performance

### What NOT to Contribute

- Proprietary code
- Examples without proper documentation
- Incomplete or broken code
- Controversial or opinionated content
- Examples that duplicate existing content

### Code Style

Follow these coding standards:

#### Groovy Style Guide

```groovy
// Use def for variable declarations
def myList = [1, 2, 3]

// Use type declarations for public APIs
public String getName() { }

// Use spaces, not tabs
indentation = '4 spaces'

// Use meaningful names
def getUserById(userId) { }

// Prefer Groovy syntax over Java
def map = [key: 'value']  // Good
def map2 = new HashMap()  // Avoid
```

#### Naming Conventions

- **Packages**: `com.example.groovyweb`
- **Classes**: `PascalCase` (e.g., `UserController`)
- **Methods**: `camelCase` (e.g., `getUserById`)
- **Constants**: `UPPER_SNAKE_CASE` (e.g., `MAX_SIZE`)
- **Variables**: `camelCase` (e.g., `userName`)

#### Documentation

```groovy
/**
 * Calculates the sum of two numbers.
 *
 * @param a First number
 * @param b Second number
 * @return Sum of a and b
 */
def sum(a, b) {
    a + b
}
```

### Commit Messages

Follow conventional commits format:

```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

**Types**: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

**Examples**:

```
feat(grails): add REST API authentication example

fix(ratpack): resolve async handler memory leak

docs: update getting started guide

test: add integration tests for user controller
```

## Pull Request Process

### 1. Create a Branch

```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/your-bug-fix
```

### 2. Make Your Changes

- Write clear, concise code
- Add/update tests
- Update documentation
- Follow style guidelines

### 3. Commit Your Changes

```bash
git add .
git commit -m "feat(category): brief description"
```

### 4. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### 5. Create Pull Request

1. Go to the repository on GitHub
2. Click "New Pull Request"
3. Select your branch
4. Fill in the PR template
5. Link related issues
6. Request review from maintainers

### Pull Request Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Code refactoring

## Testing
- [ ] Tests added/updated
- [ ] All tests pass

## Documentation
- [ ] README updated
- [ ] Documentation added

## Checklist
- [ ] Code follows style guidelines
- [ ] Self-review completed
- [ ] Comments added to complex code
- [ ] Documentation updated
- [ ] No new warnings generated
```

## Review Process

### What We Look For

1. **Code Quality**
   - Clean, readable code
   - Proper error handling
   - Efficient algorithms

2. **Documentation**
   - Clear README
   - Code comments
   - Usage examples

3. **Testing**
   - Adequate test coverage
   - Tests pass
   - Edge cases covered

4. **Consistency**
   - Matches existing style
   - Follows conventions
   - No duplication

### Feedback Timeline

- Initial response: 2-3 days
- Review completion: 1 week
- Follow-up: As needed

## Getting Help

### Resources

- [Groovy Documentation](https://groovy.apache.org/docs.html)
- [Grails Documentation](https://docs.grails.org/)
- [Ratpack Manual](https://ratpack.io/manual/)
- [Micronaut Guides](https://guides.micronaut.io/)

### Community

- GitHub Issues: Ask questions
- GitHub Discussions: Share ideas
- Groovy Community Slack: Real-time chat

## Recognition

Contributors will be:
- Listed in CONTRIBUTORS.md
- Mentioned in release notes
- Credited in examples they contribute

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

## Questions?

- Open a GitHub issue
- Start a GitHub discussion
- Contact maintainers

Thank you for contributing to Groovy Web Examples!
