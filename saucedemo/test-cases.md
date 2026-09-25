# SauceDemo Test Cases

## TC-001: Add Product to Cart

**Precondition:** User is logged in and is on the Products page.

**Test Data:** Sauce Labs Backpack

**Steps:**
1. Locate Sauce Labs Backpack.
2. Click the "Add to cart" button.
3. Open the shopping cart.

**Expected Result:** Sauce Labs Backpack is added to the cart with a quantity of 1.

**Actual Result:** Sauce Labs Backpack was successfully added to the cart with a quantity of 1.

**Result:** PASS

**Bug/Issue:** None


## TC-002: Remove Product from Cart

**Precondition:** User is logged in and the Sauce Labs Backpack is already in the cart.

**Test Data:** Sauce Labs Backpack

**Steps:**
1. Open the shopping cart.
2. Locate Sauce Labs Backpack.
3. Click the "Remove" button.

**Expected Result:** Sauce Labs Backpack is removed from the cart.

**Actual Result:** Sauce Labs Backpack was successfully removed from the cart.

**Result:** PASS

**Bug/Issue:** None


## TC-003: Add Multiple Products to Cart

**Precondition:** User is logged in and is on the Products page.

**Test Data:** Sauce Labs Bolt T-Shirt and Sauce Labs Onesie

**Steps:**
1. Locate Sauce Labs Bolt T-Shirt.
2. Click the "Add to cart" button.
3. Locate Sauce Labs Onesie.
4. Click the "Add to cart" button.
5. Open the shopping cart.

**Expected Result:** Both selected products are added to the cart.

**Actual Result:** Both selected products were successfully added to the cart.

**Result:** PASS

**Bug/Issue:** None

## Test Observation

**Observation:** The product page does not provide an option to increase the quantity of the same product before adding it to the cart. After one unit is added, the **Add to cart** button changes to **Remove**.

**Expected:** If multiple quantities of the same product are supported, the user should have an option to increase the quantity.

**Actual:** Only one unit can be added from the product page at a time.

**Classification:** Observation — not confirmed as a defect because no requirement was established stating that multiple quantities of the same product must be supported.

