
# Bug Report

## BUG-001: Checkout accepts invalid special characters in customer information fields

**Environment:** SauceDemo web application
**Testing Type:** Manual Functional Testing
**Severity:** Medium
**Priority:** Medium
**Status:** Open

### Precondition

User is logged in and has a product in the shopping cart.

### Test Data

* First Name: `@#$%`
* Last Name: `@#$%`
* ZIP Code: `@#$%`

### Steps to Reproduce

1. Log in to SauceDemo.
2. Add a product to the shopping cart.
3. Open the shopping cart.
4. Click **Checkout**.
5. Enter `@#$%` in the First Name field.
6. Enter `@#$%` in the Last Name field.
7. Enter `@#$%` in the ZIP Code field.
8. Click **Continue**.
9. Complete the checkout.
10. Open the generated order summary/PDF.

### Expected Result

The checkout form should validate the customer information fields and reject invalid input that does not meet the required format.

### Actual Result

The system accepts `@#$%` in the First Name, Last Name, and ZIP Code fields and allows the checkout to be completed successfully.

The generated PDF also displays the invalid information under the shipping details:

**SHIP TO @#$% @#$% @#$%**

### Evidence

Screenshot of the generated PDF showing the accepted invalid customer information.

### Impact

Invalid customer information can be successfully included in a completed order and displayed in the generated order document.
