# BUG-002 — Checkout allows an order to be completed with an empty cart

## Summary
The application allows the user to continue through checkout and complete an order even when the shopping cart contains no products.

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
2. The shopping cart contains no products.

## Steps to Reproduce
1. Log in to SauceDemo with `standard_user`.
2. Ensure the shopping cart is empty.
3. Open the cart and click **Checkout**.
4. Enter valid information:
   - First Name: `Yahoska`
   - Last Name: `Conrado`
   - ZIP / Postal Code: `12345`
5. Click **Continue**.
6. On **Checkout: Overview**, verify that no products are listed and review the order totals.
7. Click **Finish**.

## Expected Result
**Project acceptance criterion:** the system should prevent an order from being completed when the cart is empty. The user should be prompted to add at least one product before proceeding.

## Actual Result
The application allows checkout to proceed with no products. On **Checkout: Overview**, no product is listed and the displayed totals are:

- **Item total:** `$0.00`
- **Tax:** `$0.00`
- **Total:** `$0.00`

The **Finish** button remains enabled. After clicking it, the application shows **“Thank you for your order!”** and the dispatch message:

> Your order has been dispatched, and will arrive just as fast as the pony can get there!

The confirmation page also displays **Back Home** and **Generate PDF order**.

## Severity
**Medium** — the purchase flow can be completed without any product in the order.

## Priority
**Medium** — recommend addressing to enforce the checkout business rule.

## Reproducibility
Observed during the empty-cart checkout test.

## Impact
The application may complete an order with no purchased items, creating a potential business-rule and order-data integrity issue.

## Evidence
Save the screenshot you captured for this issue in the repository as:

`evidence/screenshots/BUG-002-Empty-Cart.png`

## Note on the expected result
SauceDemo does not show a formal empty-cart checkout requirement in its UI. The rule that an order must contain at least one product is stated as an acceptance criterion for this portfolio test project.
