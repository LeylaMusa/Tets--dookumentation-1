# QA Automation Interview & Knowledge Guide

This document summarizes core concepts for QA Automation Engineers, covering Testing Methodologies, Java Core, Selenium WebDriver, and API Testing.

---

## 1. Software Testing Fundamentals

### Edge Cases
An **edge case** is a problem or situation that occurs only at an extreme (maximum or minimum) operating parameter.
* **Example:** A field that accepts 1-100 characters being tested with exactly 1, exactly 100, or 0/101 characters.
* **Corner Case:** Occurs when multiple parameters are simultaneously at their extreme levels.

### Gherkin Style (BDD)
Used in frameworks like Cucumber to bridge the gap between technical and non-technical stakeholders.
* **Feature:** High-level description of a software feature.
* **Scenario:** A specific executable test case.
* **Steps:**
    * **Given:** Pre-conditions or initial state.
    * **When:** The action taken by the user.
    * **Then:** The expected outcome or verification.

---

## 2. Java Core for Automation

### Access Modifiers
| Modifier | Class | Package | Subclass | World |
| :--- | :---: | :---: | :---: | :---: |
| **public** | Yes | Yes | Yes | Yes |
| **protected** | Yes | Yes | Yes | No |
| **default** | Yes | Yes | No | No |
| **private** | Yes | No | No | No |

### Static vs. Instance
* **Static Methods/Fields:** Belong to the **class**. Can be called without creating an object (e.g., `Math.sqrt()`).
* **Instance Methods/Fields:** Belong to a specific **object**. Require the `new` keyword to initialize.

### Interface vs. Abstract Class
* **Interface:** A contract of "what an object can do." Supports multiple inheritance. Use for peripheral behaviors (e.g., `JSONSerializable`).
* **Abstract Class:** A blueprint of "what an object is." Use for a base identity (e.g., `BaseTest`).

### Exception Handling
* **Checked:** Must be handled at compile time (e.g., `FileNotFoundException`).
* **Unchecked (Runtime):** Occur during execution (e.g., `NullPointerException`, `ArrayIndexOutOfBoundsException`).
* **Keywords:** `try`, `catch`, `finally`, `throw`, `throws`.

---

## 3. Selenium WebDriver

### Locators: CSS vs. XPath
* **CSS Selectors:** Faster, cleaner syntax. Preferred for most UI elements.
* **XPath:** Can navigate backwards (to parents) and search by text (e.g., `//button[text()='Submit']`). Slower but more powerful.

### Synchronization (Waiters)
1.  **Implicit Wait:** Global wait time for the entire driver session.
2.  **Explicit Wait:** Waiting for a specific `ExpectedCondition` (e.g., `elementToBeClickable`).
3.  **Fluent Wait:** Explicit wait with a custom polling frequency and ignored exceptions.

### WebDriver Architecture
The code communicates with the **Browser Driver** (e.g., ChromeDriver) via the **W3C Protocol**, which then controls the actual **Browser Engine** (Blink, Gecko, WebKit).

---

## 4. API Testing (REST)

### HTTP Methods & Idempotency
An operation is **idempotent** if multiple identical requests have the same effect as a single request.
* **GET:** Idempotent (Retrieves data).
* **PUT:** Idempotent (Replaces resource).
* **DELETE:** Idempotent (Removes resource).
* **POST:** **Not** Idempotent (Creates new resources).

### Tools
* **Postman:** GUI for manual and automated API suite execution.
* **cURL:** Command-line tool for transferring data via various protocols.
* **RestAssured:** Java library for testing and validating REST services.

---

## 5. Test Framework Comparison
| Tool | Primary Language | Note |
| :--- | :--- | :--- |
| **JUnit/TestNG** | Java | Unit/Integration testing engines. |
| **Pytest** | Python | Highly extensible and concise. |
| **NUnit** | C# | Standard for .NET environments. |
| **Robot Framework** | Python/Custom | Keyword-driven, easy for non-coders. |
