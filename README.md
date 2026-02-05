# Factory Robot Hazard Analyzer

## Project Overview
The Factory Robot Hazard Analyzer is a Java console-based application that evaluates the
hazard risk score of a factory robot based on three key parameters:

- **Arm Precision** – Accuracy of the robot arm movement
- **Worker Density** – Number of workers near the robot
- **Machinery State** – Condition of the machinery (Worn, Faulty, Critical)

The application validates inputs, calculates the hazard risk score using a predefined
formula, and handles invalid scenarios using a custom exception.  
The project is developed **use case by use case (UC-wise)** to demonstrate Object-Oriented
Programming (OOPS) concepts, clean code practices, and GitFlow-based version control.

---

## Problem Statement
To develop a Factory Robot Hazard Analyzer system that:
- Validates all inputs
- Calculates a hazard risk score
- Handles invalid scenarios using a custom exception
- Demonstrates modular, OOPS-compliant design

---

## Hazard Risk Calculation
The hazard risk score is calculated using the formula: `Hazard Risk = ((1.0 - armPrecision) * 15.0) + (workerDensity * machineRiskFactor)`

---

### Machine Risk Factors
| Machinery State | Risk Factor |
|-----------------|------------|
| Worn            | 1.3        |
| Faulty          | 2.0        |
| Critical        | 3.0        |

---

## Development Process
This project strictly follows:
- **Use Case–wise incremental development**
- **Code refactoring at each UC**
- **GitFlow branching model**
- **Clean and meaningful commit history**

Each use case is implemented in a separate `feature/UCx` branch and merged into the
`dev` branch after completion.

---

## Use Case Implementation Details

### UC1: Display Static Hazard Message
**What was done:**
- Displayed a static message indicating the purpose of the application.

**How it was done:**
- Created the main class and printed a simple message using `System.out.println()`.

---

### UC2: Accept Robot Hazard Inputs
**What was done:**
- Accepted user inputs for arm precision, worker density, and machinery state.

**How it was done:**
- Used the `Scanner` class to read input values from the console.
- Stored inputs without validation.

---

### UC3: Calculate Hazard Risk Score (No Validation)
**What was done:**
- Implemented the hazard risk calculation logic.

**How it was done:**
- Applied the given formula directly assuming inputs were valid.
- Used conditional logic to map machinery state to its risk factor.

---

### UC4: Input Validation Using Conditional Logic
**What was done:**
- Added validation checks for all inputs.

**How it was done:**
- Used `if-else` conditions inside the main method.
- Displayed error messages for invalid inputs.
- Identified drawbacks such as cluttered main method.

---

### UC5: Refactor Validation into a Separate Method
**What was done:**
- Moved calculation and validation logic into a separate method.

**How it was done:**
- Created a method to encapsulate business logic.
- Reduced complexity of the `main()` method.
- Improved separation of concerns.

---

### UC6: Introduce Custom Exception (RobotSafetyException)
**What was done:**
- Introduced a custom exception to handle invalid scenarios.

**How it was done:**
- Created `RobotSafetyException` extending `Exception`.
- Replaced print-based error handling with `throw` and `catch`.

---

### UC7: Machinery State Risk Mapping & Auditor Class
**What was done:**
- Separated business logic into a dedicated auditor class.

**How it was done:**
- Created `RobotHazardAuditor` class.
- Encapsulated validation and calculation logic.
- Ensured machinery state handling was case-sensitive.

---

### UC8: Fully Modular & OOPS-Compliant Hazard Analyzer
**What was done:**
- Finalized a clean, modular, and extensible system.

**How it was done:**
- Main class handles input and output.
- Auditor class handles business logic.
- Custom exception handles validation errors.
- Ensured compliance with OOPS principles and problem constraints.

---

## OOPS Principles Demonstrated
- **Encapsulation** – Business logic encapsulated within classes
- **Abstraction** – Users interact through method calls
- **Single Responsibility Principle** – Each class has one role
- **Modularity** – Easy to maintain and extend

---

## Branching Strategy (GitFlow)
- **main**: Contains only documentation and configuration files
- **dev**: Contains the latest stable implementation (final UC)
- **feature/UCx**: Individual use case implementation branches

---

## How to Run the Application
```bash
javac FactoryRobotHazardAnalyzer.java
java FactoryRobotHazardAnalyzer