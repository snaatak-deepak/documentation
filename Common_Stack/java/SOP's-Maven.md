# Maven Standard Operating Procedure (SOP)

## Metadata

| **Author**        | **Created on** | **Version** | **Last Updated** |
|-------------------|----------------|-------------|------------------|
| Deepak Kushwaha   | 18-07-2025     | v1.0        | 18-07-2025       |

---

## Table of Contents

- [ Introduction](#-introduction)
- [ Prerequisites](#️-1-prerequisites)
- [ Commonly Used Maven Commands](#-2-commonly-used-maven-commands)
- [ Debugging & Diagnostic Commands](#-3-debugging--diagnostic-commands)
- [ Dependency Management Commands](#-4-dependency-management-commands)
- [ Build Lifecycle Phases](#-5-build-lifecycle-phases)
- [ Tips & Best Practices](#-6-tips--best-practices)
- [ Reference Links](#-7-reference-links)

---

## Introduction

**Maven** is a powerful project management and build automation tool primarily used in Java environments. It simplifies the process of building, testing, and deploying applications by managing project structure, dependencies, plugins, and build lifecycles through a declarative approach using a `pom.xml` file.

---

## Prerequisites

- Java Development Kit (JDK) 8 or higher
- Apache Maven installed and added to system `PATH`
- Verify installation:

```bash
mvn -v
```

---

## Commonly Used Maven Commands

| Task                        | Command                      |
|-----------------------------|------------------------------|
| Clean previous builds       | `mvn clean`                  |
| Compile source code         | `mvn compile`                |
| Run unit tests              | `mvn test`                   |
| Package into JAR/WAR        | `mvn package`                |
| Install to local repo       | `mvn install`                |
| Deploy to remote repo       | `mvn deploy`                 |
| Skip tests                  | `mvn install -DskipTests`    |
| Run with multiple goals     | `mvn clean package`          |
| Run Java class via plugin   | `mvn exec:java`              |

---

## Debugging & Diagnostic Commands

| Purpose                        | Command                        |
|--------------------------------|--------------------------------|
| Debug with verbose output      | `mvn clean install -X`         |
| Show effective POM             | `mvn help:effective-pom`       |
| View active Maven profiles     | `mvn help:active-profiles`     |
| Force download from remote     | `mvn clean install -U`         |
| View complete dependency tree  | `mvn dependency:tree`          |
| Analyze dependency usage       | `mvn dependency:analyze`       |
| Print system and env info      | `mvn help:system`              |

---

## Dependency Management Commands

**Add dependencies manually in `pom.xml` under:**

```xml
<dependencies>
  <dependency>
    <groupId>org.example</groupId>
    <artifactId>library</artifactId>
    <version>1.0.0</version>
  </dependency>
</dependencies>
```

**Resolve/download all declared dependencies:**

```bash
mvn dependency:resolve
```

**Analyze unused or undeclared dependencies:**

```bash
mvn dependency:analyze
```

---

## Build Lifecycle Phases

| Phase     | Description                                 |
|-----------|---------------------------------------------|
| validate  | Validate the project is correct and complete|
| compile   | Compile source code                         |
| test      | Run unit tests                              |
| package   | Package code into JAR/WAR                   |
| verify    | Perform integration tests or quality checks |
| install   | Install package to local Maven repository   |
| deploy    | Copy to remote repository for sharing       |

---

## Tips & Best Practices

- Use `mvn clean` before `compile` or `install` to avoid stale builds.
- Use `-DskipTests` to skip test execution while still compiling test classes.
- Use profiles in `pom.xml` to manage different environment configs:

  ```bash
  mvn clean install -Pdev
  ```
- Maintain a parent POM in multi-module projects to centralize config.
- Automate builds using Jenkins, GitHub Actions, or GitLab CI with goals like:

  ```bash
  mvn clean verify
  ```

---

## Reference Links

- [Official Docs](https://maven.apache.org/guides/)
- [Maven Central Search](https://mvnrepository.com/)
- **CLI Help:**

  ```bash
  mvn --help
  ```

## Author

- [Deepak Kushwaha](#)

