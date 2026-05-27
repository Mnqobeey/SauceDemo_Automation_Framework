# SauceDemo Selenium Automation Framework

A Java-based UI automation framework for the SauceDemo checkout journey. The project uses Selenium WebDriver, Cucumber, JUnit, Maven, and the Page Object Model to keep test logic readable and maintainable.

## Problem It Solves

Manual regression checks for login, cart, and checkout flows are repetitive and easy to miss. This framework automates the core purchase path so the same user journey can be executed consistently in local development or CI.

## Tech Stack

- Java 17
- Maven
- Selenium WebDriver
- Cucumber / Gherkin
- JUnit
- WebDriverManager
- Jenkins pipeline support

## Framework Structure

```text
src/test/java/com/mnqobeey/saucedemo
|-- config      # Runtime configuration loader
|-- core        # WebDriver setup and lifecycle
|-- hooks       # Cucumber setup/teardown hooks
|-- pages       # Page Object Model classes
|-- runners     # Cucumber JUnit runner
`-- steps       # Step definitions

src/test/resources
|-- config      # Test configuration
|-- features    # Gherkin feature files
`-- log4j2.properties
```

## Key Features

- BDD scenario for a full SauceDemo checkout flow.
- Page Object Model classes for login, inventory, cart, and checkout pages.
- Config-driven runtime values through properties, system properties, or environment variables.
- Automatic ChromeDriver management with WebDriverManager.
- Headless mode support for CI execution.
- HTML, JSON, and JUnit XML Cucumber reports.
- Failure screenshots attached to Cucumber scenarios.

## Test Coverage

Current sample coverage focuses on the happy-path checkout journey:

1. Open the SauceDemo login page.
2. Log in with the public SauceDemo demo user.
3. Add two products to the cart.
4. Validate cart contents.
5. Complete checkout information.
6. Finish the order and verify the success message.

## Public Demo Credentials

The default credentials in `src/test/resources/config/test.properties` are SauceDemo's published demo credentials:

```properties
saucedemo.username=standard_user
saucedemo.password=secret_sauce
```

They are kept in the repository because they are intended for public test automation practice and are not private account credentials.

## Run Tests

Prerequisites:

- Java 17 installed
- Maven installed
- Chrome installed

Run the test suite:

```bash
mvn test
```

Run in headless mode:

```bash
mvn test -Dheadless=true
```

Override configuration from the command line:

```bash
mvn test -Dheadless=true -Dbrowser=chrome
```

Configuration values can also be supplied as environment variables. For example, `saucedemo.username` maps to `SAUCEDEMO_USERNAME`.

## Reports

After a test run, reports are generated under `target/`:

- `target/cucumber-report.html`
- `target/cucumber-report.json`
- `target/cucumber-report.xml`
- `target/surefire-reports/`

Open `target/cucumber-report.html` in a browser to review the readable Cucumber report.

## Project Status

Portfolio-ready QA automation project for demonstrating Selenium, Cucumber, Maven, Page Object Model design, and CI-friendly test execution against a public demo application.

## What I Learned

- Structuring Selenium tests with Page Object Model classes.
- Writing readable BDD scenarios with Cucumber.
- Managing browser setup and teardown safely with hooks.
- Using Maven and JUnit to run repeatable automated checks.
- Producing reports that are useful for QA review and CI pipelines.
