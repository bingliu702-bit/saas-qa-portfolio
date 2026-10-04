# Day 01 — Software Testing Basics

## 1. What Is Software Testing?

Software testing is the process of evaluating software by reviewing requirements, executing functions, comparing actual results with expected results, identifying potential defects, and assessing product quality and risk.

Software testing does not only take place before a product is released. It can also occur during requirements analysis, development, release, and post-release maintenance.

The goal of testing is not to prove that software is completely defect-free. Instead, testing helps identify defects as early as possible, reduce product risk, and provide useful information for release decisions.

---

## 2. Testing vs. Debugging

### Testing

Testing is the process of evaluating software to identify unexpected behavior, verify requirements, and assess quality and risk.

Testers design test scenarios, execute tests, compare actual results with expected results, and document the issues they discover.

### Debugging

Debugging is the process of locating the root cause of a problem and modifying the code or other work products to fix it.

Debugging is usually performed by developers.

### Difference

Testing mainly answers:

> Where does the software behave incorrectly, and what is the associated risk?

Debugging mainly answers:

> Why did the problem occur, and how should it be fixed?

Testing can identify a failure and provide evidence of a possible defect, but a tester does not necessarily know which line of code caused the problem.

Developers use debugging to identify and fix the underlying cause.

---

## 3. Error, Defect, and Failure

### Error

An error is a human mistake made during requirements analysis, design, coding, testing, or other activities.

**Example:**

A requirement states that a product should receive a 10% discount, but a developer misunderstands the requirement and implements a fixed $10 discount instead.

### Defect

A defect is a flaw in a requirement, design, code, or other work product that may cause the software to behave incorrectly.

**Example:**

The checkout logic calculates the discount as "original price minus $10" instead of applying a 10% discount.

### Failure

A failure is an observable incorrect behavior of the software during execution, where the actual result differs from the expected result.

**Example:**

A product with an original price of $100 should cost $90 after a 10% discount, but the checkout page displays $95.

### Relationship

The concepts can be understood as:

**Human Error**  
↓  
**Defect in a Work Product**  
↓  
**Failure During Software Execution**

---

## 4. Why Testing Cannot Prove That Software Has No Defects

Testing can only evaluate the conditions and scenarios that have been designed and executed.

Real users may use different devices, browsers, data, operation sequences, network conditions, and environments.

Because software can have a very large number of possible input combinations and usage paths, it is usually impossible to test every possible situation.

Therefore, not finding a bug does not prove that the software contains no defects.

It only means that no defect was found under the conditions that were tested.

---

## 5. Example

### Scenario

A developer implements the product discount calculation incorrectly, and the customer sees an incorrect price during checkout.

- **Error:** The developer misunderstands the discount requirement or makes a mistake while implementing the calculation.
- **Defect:** The incorrect discount calculation logic is introduced into the checkout code.
- **Failure:** When the software runs, the checkout page displays an incorrect final price.

---

## 6. Testing Activities

### 1. Test Planning

Define the test objectives, scope, approach, resources, schedule, people involved, and tools required.

### 2. Test Monitoring and Control

Monitor testing progress and risk against the test plan. Take corrective actions or adjust the plan when necessary.

### 3. Test Analysis

Review requirements and the product to identify what needs to be tested, including relevant features, conditions, and risks.

### 4. Test Design

Design test scenarios, test cases, test data, and expected results based on the test conditions identified during test analysis.

### 5. Test Implementation

Prepare the test cases and supporting materials for execution, including test data, accounts, environments, and execution order.

### 6. Test Execution

Execute the tests, compare actual results with expected results, record test outcomes, and report any defects found.

### 7. Test Completion

Determine whether the test objectives and completion criteria have been met, summarize the results and remaining risks, and organize the test documentation.

---

## 7. Test Activity Flow

Test Planning  
↓  
Test Monitoring and Control  
↓  
Test Analysis  
↓  
Test Design  
↓  
Test Implementation  
↓  
Test Execution  
↓  
Test Completion
