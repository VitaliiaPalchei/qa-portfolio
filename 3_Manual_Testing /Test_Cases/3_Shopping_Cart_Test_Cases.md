## TC-CART-01: Add Product to Cart from PLP

**Preconditions:**
- Product is in stock.

**Steps:**
1. Open the website homepage.
2. Open any product category.
3. Click the Add to Cart button on a product tile.

**Expected Result:**
- Product is added to the cart.
- Confirmation message is displayed.
- Cart icon updates with the correct item count.

## TC-CART-02: Add Product to Cart from PDP

**Preconditions:**
- Product is in stock.

**Steps:**
1. Open the website homepage.
2. Open any category.
3. Open a product details page (PDP).
4. Click the Add to Cart button.

**Expected Result:**
- Product is added to the cart.
- Confirmation message appears at the top of the page.
- Cart icon updates correctly.

## TC-CART-03: View Cart Contents

**Preconditions:**
- At least one product is added to the cart.

**Steps:**
1. Click the cart icon to open the Cart page.

**Expected Result:**
- Cart page displays:
          Product image
          Product name
          Unit price
          Quantity field
          Total price per item
- Cart subtotal is calculated correctly.

## TC-CART-04: Change Product Quantity in Cart

**Preconditions:**
- Product exists in the cart.
  
**Steps:**
1. Open the Cart page.
2. Change the quantity of a product.

**Expected Result:**
- Product quantity updates successfully.
- Item total updates correctly.
- Cart subtotal recalculates automatically.

## TC-CART-05: Remove Product from Cart

**Preconditions:**
- Product exists in the cart.
  
**Steps:**
1. Open the website homepage.
2. Navigate to the Shopping Cart page.
3. Select the checkbox next to the product to be removed.
4. Click the Remove button.

**Expected Result:**
- Product is removed from the cart.
- Cart subtotal updates correctly.

## TC-CART-06: Apply Discount Coupon Code

**Preconditions:**
- Product exists in the cart.
- A valid coupon code is available.
  
**Steps:**
1. Open the Cart page.
2. Enter a valid coupon code.
3. Click Apply.
   
**Expected Result:**
- Discount is applied successfully.
- Updated total price is displayed.
- Confirmation or success message appears.

## TC-CART-07: Apply Invalid Coupon Code

**Preconditions:**
- Product exists in the cart.
  
**Steps:**
1. Open the Cart page.
2. Enter an invalid or expired coupon code.
3. Click Apply.
   
**Expected Result:**
- The coupon is not applied.
- The validation error message is displayed.

## TC-CART-08: Estimate Shipping Cost

**Preconditions:**
- Product exists in the cart.
  
**Steps:**
1. Open the Cart page.
2. Enter shipping details (Country, State/Region).
3. Click Estimate Shipping.
   
**Expected Result:**
- Available shipping options are displayed.

## TC-CART-09: Proceed to Checkout with Accepted Terms

**Preconditions:**
- At least one product is in the cart.
  
**Steps:**
1. Open the Cart page.
2. Select the checkbox “I agree with the terms of service and I adhere to them unconditionally.”
3. Click Proceed to Checkout.
   
**Expected Result:**
- User is allowed to proceed.
- User is redirected to the Checkout page.

## TC-CART-10: Checkout Blocked Without Accepting Terms

**Preconditions:**
- At least one product is in the cart.
  
**Steps:**
1. Open the Cart page.
2. Do not select the Terms of Service checkbox.
3. Click Proceed to Checkout.
   
**Expected Result:**
- User is not redirected to checkout.
- Validation message appears (e.g., “You must agree to the terms of service before proceeding.”).


