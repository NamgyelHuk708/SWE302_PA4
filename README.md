# CI/CD Demo Project

[![Java CI with Maven](https://github.com/NamgyelHuk708/SWE302_PA4/actions/workflows/maven.yml/badge.svg)](https://github.com/NamgyelHuk708/SWE302_PA4/actions/workflows/maven.yml)
[![Security Scan](https://img.shields.io/badge/security-snyk-4c1?style=flat-square)](https://github.com/NamgyelHuk708/SWE302_PA4/security/code-scanning)

## Overview

This is a Spring Boot application demonstrating CI/CD practices with integrated Static Application Security Testing (SAST) using Snyk.

## Features

- **Automated Testing**: Unit tests run on every push and pull request
- **Security Scanning**: Snyk SAST integration for vulnerability detection
- **Dependency Monitoring**: Continuous monitoring of project dependencies
- **Scheduled Scans**: Weekly security scans every Monday
- **GitHub Security Integration**: Results uploaded to GitHub Security tab

## Tech Stack

- **Framework**: Spring Boot 3.4.11
- **Java Version**: 17
- **Build Tool**: Maven
- **Security**: Snyk SAST
- **CI/CD**: GitHub Actions

## Dependencies

- Spring Web
- DataFaker (for generating random data)
- JaCoCo (for code coverage)

## Getting Started

### Prerequisites

- Java 17 or higher
- Maven 3.6+

### Build and Run

```bash
# Clone the repository
git clone https://github.com/NamgyelHuk708/SWE302_PA4.git
cd SWE302_PA4

# Build the project
mvn clean compile

# Run tests
mvn test

# Start the application
mvn spring-boot:run
```

The application will start on `http://localhost:8080`

## Security

This project uses Snyk for security scanning:

- **Dependency Scanning**: Identifies vulnerabilities in project dependencies
- **Code Scanning**: Static analysis for security issues in source code
- **Continuous Monitoring**: Tracks project in Snyk for new vulnerabilities
- **Automated Remediation**: Suggests fixes for detected issues

### Security Configuration

Security policies are managed in the `.snyk` file. View current vulnerabilities and security status in the [Security tab](https://github.com/NamgyelHuk708/SWE302_PA4/security).

## CI/CD Pipeline

The project includes a comprehensive CI/CD pipeline:

1. **Code Changes Detection**: Runs only when relevant files change
2. **Build & Test**: Compiles code and runs unit tests
3. **Security Analysis**: 
   - Dependency vulnerability scanning
   - Code security scanning
4. **Results Upload**: Security findings sent to GitHub Security
5. **Monitoring**: Production dependencies tracked in Snyk

### Workflow Triggers

- **Push to main**: Full pipeline execution
- **Pull Requests**: Full pipeline execution
- **Weekly Schedule**: Security scans every Monday at 2 AM UTC

## Project Structure

```
├── .github/
│   └── workflows/
│       └── maven.yml          # CI/CD workflow
├── src/
│   ├── main/java/
│   │   └── sg/edu/nus/iss/cicddemo/
│   │       ├── CicdDemoApplication.java
│   │       └── Controller/
│   │           └── DataController.java
│   └── test/java/
├── .snyk                      # Snyk configuration
├── pom.xml                    # Maven configuration
└── dockerfile                 # Docker configuration
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests: `mvn test`
5. Submit a pull request

All pull requests will be automatically scanned for security vulnerabilities.

## License

This project is part of the NUS-ISS Software Engineering Practice and Tools (SWE302) course.

---

**Last Updated**: November 2025
