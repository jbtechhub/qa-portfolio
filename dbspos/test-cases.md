# DBSPOS Test Cases

## Product Creation API

### TC-001: Create Product With Required Information

**Objective:** Verify that a product can be created when the required information is provided.

**Precondition:** User is authenticated and the Product Creation API is accessible.

**Test Data:**

* Product Name: Product Rice
* Buy Price: ₱45
* Sell Price: ₱50
* Stock: Not provided
* Barcode: Not provided

**Steps:**

1. Send a POST request to `/products`.
2. Provide the product name, buy price, and sell price.
3. Do not provide stock or barcode.
4. Submit the request.

**Expected Result:**
The product should be created successfully. Stock should default to 0 and a system-generated barcode should be assigned.

**Actual Result:**
Product was created successfully with stock 0 and a system-generated barcode.

**Result:** PASS

### TC-002: Reject Product When Selling Price Is Lower Than Buying Price

**Objective:** Verify that the system does not allow a selling price lower than the buying price.

**Precondition:** User is authenticated and the Product Creation API is accessible.

**Test Data:**

* Product Name: Release API Price Test
* Buy Price: ₱300
* Sell Price: ₱250
* Stock: 5

**Steps:**

1. Send a POST request to `/products`.
2. Enter ₱300 as the buy price.
3. Enter ₱250 as the sell price.
4. Enter 5 as the stock.
5. Submit the request.

**Expected Result:**
The API should reject the request and should not create the product.

**Actual Result:**
The API accepted the request and created the product even though the selling price was lower than the buying price.

**Result:** FAIL

**Related Bug:** BUG-001

### TC-003: Reject Product When Product Name Already Exists

**Objective:** Verify that the Product Creation API does not allow duplicate product names.

**Precondition:** User is authenticated and the Product Creation API is accessible. An existing product named **Shampoo 15ml** is already in the system.

**Test Data:**

* Product Name: Shampoo 15ml
* Buy Price: ₱8
* Sell Price: ₱10
* Stock: 5

**Steps:**

1. Send a POST request to `/products`.
2. Enter an existing product name: `Shampoo 15ml`.
3. Enter ₱8 as the buy price.
4. Enter ₱10 as the sell price.
5. Enter 5 as the stock.
6. Submit the request.

**Expected Result:** The API should reject the request because the product name already exists. No duplicate product should be created.

**Actual Result:** During initial testing, the API accepted the request and created a duplicate product with the same name.

**Result:** PASS

**Retest Result:** PASS — After the backend duplicate-name validation fix, the API rejected the request with HTTP 400 and returned `"Product already exists"`.

**Related Bug:** BUG-002
