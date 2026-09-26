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
