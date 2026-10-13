# SauceDemo Web Application — QA Testing Project

## 1. General Information

- **Project Name:** SauceDemo Web Application — QA Testing Project
- **Specialty:** Quality Assurance (QA)
- **Project Type:** Manual Web Application Testing
- **Application Under Test:** SauceDemo
- **Original Application Link:** https://www.saucedemo.com/
- **Published Project Link:** (https://github.com/guisselle9282/saucedemo-qa-testing/edit/main/README.md)
-  **Testing Environment:** Google Chrome on a Windows laptop
- **Testing Approach:** Manual Functional Testing

## 2. Objective

The objective of this project is to evaluate the main functionalities of the SauceDemo web application, including login, product selection, shopping cart operations, and checkout.

The project aims to identify behaviors that could affect the checkout experience, particularly the acceptance of invalid ZIP Code formats and the ability to complete an order with an empty cart.

## 3. Work Plan

### Step 1 — Initial Exploration and Requirements Analysis
Explore the application, identify its main user flows, and define the testing scope. Where formal requirements were not available, establish explicit acceptance criteria for the tests.

### Step 2 — Test Preparation
Design test cases for login, product catalog, sorting, product details, shopping cart, checkout, order completion, and navigation.

Apply positive testing, negative testing, exploratory testing, equivalence partitioning, and boundary value analysis.

### Step 3 — Test Execution
Execute the test cases manually using Google Chrome on a Windows laptop. Record the actual results and compare them with the expected results.

### Step 4 — Evaluation
Classify test results as PASS, FAIL, or OBSERVATION. Document defects, assess their severity and priority, and associate screenshots with the relevant bug reports.

### Step 5 — Conclusions and Next Steps
Summarize the test results, identify improvement opportunities, and recommend additional testing, including cross-browser testing, API testing, and automation.

## 4. Key Questions

1. Can users complete the main shopping flow successfully when they provide valid information?
2. Does the checkout form reject invalid ZIP Code values and prevent an order from being completed with an empty cart?
3. Are product information, order totals, and order confirmation displayed consistently throughout the purchase flow?

## 5. What Was Done and How

### Types of Testing
- Functional testing
- Exploratory testing
- Positive testing
- Negative testing
- End-to-end testing

### Test Design Techniques
- Equivalence partitioning
- Boundary value analysis

### Tools and Environment
- **Application:** SauceDemo
- **Browser:** Google Chrome
- **Operating System:** Windows
- **Device:** Laptop
- **Test Documentation:** Microsoft Excel-compatible test case spreadsheet
- **Evidence:** Screenshots captured during manual execution
- **Version Control and Publication:** GitHub

### Acceptance Criteria
The test cases define expected behavior for the application's main user flows. When formal requirements were unavailable, project-specific acceptance criteria were defined and documented.

For example:
- Invalid ZIP Code values should be rejected.
- An order should not be completed when the shopping cart is empty.
- A valid checkout should display the selected product and a consistent order total.

## 6. Results

A total of **28 test cases** were recorded and executed.

| Test Status | Number of Cases | Percentage |
|---|---:|---:|
| PASS | 21 | 75.00% |
| FAIL | 5 | 17.86% |
| OBSERVATION | 2 | 7.14% |
| **Total** | **28** | **100%** |

### Main Findings

#### BUG-001 — Checkout Accepts Invalid ZIP Code Formats
**Severity:** Medium  
**Priority:** Medium

The checkout form accepted invalid values such as `ABCDE`, `1`, `1234`, and `123456` without displaying a validation error. The user could continue through checkout and complete the order.

The expected five-digit numeric format is an acceptance criterion defined for this project, not a claim about an official published SauceDemo requirement.

[View BUG-001](bug-reports/BUG-001-Invalid-ZIP.md)

#### BUG-002 — Checkout Allows Order Completion with an Empty Cart
**Severity:** Medium  
**Priority:** Medium

The application allowed the checkout process to continue with no products in the cart. The overview displayed an item total of `$0.00`, tax of `$0.00`, and a total of `$0.00`. The Finish action remained available, and the order confirmation page was displayed.

The expectation that an order must contain at least one product is an acceptance criterion defined for this project.

[View BUG-002](bug-reports/BUG-002-Empty-Cart-Checkout.md)

### Test Artifacts

- [Test Cases Spreadsheet](test-cases/SauceDemo_QA_Test_Cases.xlsx)
- [Test Execution Summary](test-results/test-execution-summary.md)
- [Bug Report — Invalid ZIP Code](bug-reports/BUG-001-Invalid-ZIP.md)
- [Bug Report — Empty Cart Checkout](bug-reports/BUG-002-Empty-Cart-Checkout.md)
- [Test Evidence and Screenshots](evidence/screenshots/)

### Scope and Limitations

This project focused on manual functional testing of the main shopping flow. Performance and load testing, backend and database testing, deep security testing, accessibility testing, automated testing, and broad cross-browser testing were not included.

## 7. Conclusions

This project provided practical experience in planning and executing manual functional tests, documenting test cases, applying test design techniques, comparing expected and actual results, and reporting defects with reproducible steps and supporting evidence.

The results show that the main shopping flow can be completed with valid information, while the tested checkout scenarios also revealed two behaviors that violate the acceptance criteria defined for this project.

Future improvements could include expanding browser and device coverage, consulting formal requirements, adding accessibility and performance testing, testing APIs, and automating regression scenarios.

**Interview Highlight:** I executed and documented 28 manual test cases for a web application, applied negative testing and boundary value analysis, and reported two checkout defects with steps to reproduce, severity, priority, and supporting evidence.

## 8. Project Checklist

- [x] README includes project information, objective, work plan, key questions, methodology, results, and conclusions.
- [x] Test cases are documented in an Excel spreadsheet.
- [x] Two bug reports are documented.
- [x] Test execution results are summarized.
- [x] The original application link is included.
- [x] Test evidence folder is organized.
- [ ] Published GitHub repository URL is verified and recorded.
- [x] Screenshots are uploaded and linked to the corresponding bug reports.
- [ ] Coach or tutor link is added if required by the course.
- [x] No personal account passwords or access tokens are included.

**Original Application:** https://www.saucedemo.com/

**GitHub Repository:** Replace the placeholder in General Information with the actual URL of this repository.

**Coach/Tutor Link:** Add the link provided by your course if your tutor requires it.
