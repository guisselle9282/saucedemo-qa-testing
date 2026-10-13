# SauceDemo QA Testing — Test Execution Summary

## Project and environment
- **Application:** SauceDemo — https://www.saucedemo.com/
- **Specialty:** Quality Assurance (QA)
- **Test approach:** Manual functional testing
- **Browser:** Google Chrome
- **Operating system:** Windows
- **Device:** Laptop
- **Test account used:** `standard_user` (with the public SauceDemo practice credentials)

## Execution summary

| Status | Count |
|---|---:|
| PASS | 21 |
| FAIL | 5 |
| OBSERVATION | 2 |
| **Total test cases** | **28** |

These counts represent the 28 test cases recorded in `test-cases/SauceDemo_QA_Test_Cases.xlsx`.

## Main findings

### BUG-001 — Checkout accepts invalid ZIP Code formats
The checkout form accepted `ABCDE`, `1`, `1234`, and `123456` without displaying a validation message. The five-digit numeric format `12345` was also accepted. The expected five-digit numeric rule is an acceptance criterion defined for this portfolio project; it is not being presented as an official published SauceDemo requirement.

### BUG-002 — Checkout allows an order to be completed with an empty cart
The checkout flow allowed the user to reach the overview with no products, showed Item total `$0.00`, Tax `$0.00`, and Total `$0.00`, and allowed the user to select Finish and reach the order confirmation page. The expectation that an order must contain at least one product is an acceptance criterion defined for this portfolio project.

## Test techniques used
- Positive testing
- Negative testing
- Exploratory testing
- Equivalence partitioning
- Boundary value analysis
- End-to-end testing

## Scope tested
Login, product catalog and details, product sorting, shopping cart, checkout required-field validation, ZIP format behavior, order overview, order completion, empty-cart checkout, and basic navigation.

## Limitations
Testing was performed manually in Google Chrome on a Windows laptop. Performance/load testing, backend/database testing, deep security testing, broad cross-browser coverage, and mobile testing were outside this project's scope.
