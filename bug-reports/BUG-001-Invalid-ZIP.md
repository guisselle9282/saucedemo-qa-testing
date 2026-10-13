# BUG-001 — Checkout accepts invalid ZIP Code formats

## Summary
The checkout form accepts ZIP/Postal Code values that do not match the five-digit format used as the acceptance criterion for this QA project. It displays no validation error and allows the order flow to continue.

## Environment
- **Application:** SauceDemo — https://www.saucedemo.com/
- **Test type:** Web application testing
- **Approach:** Manual functional testing
- **Browser:** Google Chrome
- **Operating system:** Windows
- **Device:** Laptop
- **Test user:** `standard_user`

## Preconditions
1. The user is logged in as `standard_user`.
2. At least one product is in the shopping cart.
3. The user is on the Checkout: Your Information page.

## Test data
| ZIP / Postal Code | Observed behavior |
|---|---|
| `1` | Continue allowed |
| `1234` | Continue allowed |
| `12345` | Continue allowed |
| `123456` | Continue allowed |
| `ABCDE` | Continue allowed |

## Steps to Reproduce
1. Log in to SauceDemo with `standard_user`.
2. Add **Sauce Labs Backpack** to the cart.
3. Open the cart and click **Checkout**.
4. Enter `Yahoska` as First Name.
5. Enter `Conrado` as Last Name.
6. Enter an invalid ZIP value, for example `ABCDE`.
7. Click **Continue**.
8. Observe the Checkout: Overview page and continue through **Finish**.

## Expected Result
**Project acceptance criterion:** the ZIP / Postal Code field accepts exactly five numeric digits. Values with letters or an incorrect length should be rejected, an informative validation message should appear, and the user should not be able to continue until the field is corrected.

## Actual Result
The application accepts `ABCDE`, `1`, `1234`, and `123456` without displaying a validation error. The user can continue to **Checkout: Overview**, reach **Finish**, and complete the order.

## Severity
**Medium** — invalid checkout data is accepted without feedback.

## Priority
**Medium** — recommend addressing as part of checkout form validation.

## Reproducibility
Reproduced with all five ZIP values listed in the test-data table during this test session.

## Impact
Incorrectly formatted postal-code data can be submitted without user feedback, potentially reducing customer-data quality.

## Evidence
Save the screenshot you captured for this issue in the repository as:

`evidence/screenshots/BUG-001-ZIP.png`

## Note on the expected result
SauceDemo does not show a formal ZIP-validation requirement in its UI. The five-digit numeric rule above is an explicit acceptance criterion defined for this portfolio test project, rather than a claim about a documented SauceDemo requirement.
