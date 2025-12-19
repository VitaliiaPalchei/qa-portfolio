 # Search Test Cases


## TC-SR-01: Search with Valid Keyword

**Steps:**
1. Open the website homepage.
2. Enter a valid keyword (e.g., book) in the search field.
3. Submit the search.

**Expected Result:**
- Search Results page loads successfully.
- Products matching the entered keyword are displayed.


# Product Browsing (PLP – Product Listing Page)


## TC-PB-02: Verify Category Page Opens and Displays Product List

**Steps:**
1. Open the website homepage.
2. Click any product category from the top navigation menu or side category list.

**Expected Result:**
- The selected category page opens successfully.
- A list of products is displayed.
- Each product appears as a separate product tile.

## TC-PB-03: Verify Product Tile Displays Required Elements

**Steps:**
1. Open the website homepage.
2. Navigate to any category page containing products.
3. 
**Expected Result:**
 - Each product tile displays:
       Product image
       Product name
       Product price
       Rating stars 
       Add to Cart button

## TC-PB-04: Add Product to Cart from Product Listing Page

**Steps:**
1. Open the website homepage.
2. Navigate to any category (e.g., Books).
3. Click the Add to Cart button on a product tile.
   
**Expected Result:**
- Product is added to the cart
- Confirmation message appears.
- Cart icon updates the item count.
- User remains on the category page.

## TC-PB-05: Sort Products by Price (Low to High)

**Steps:**
1. Open the website homepage.
2. Navigate to any product category.
3. Select Price: Low to High from the sorting dropdown.
   
**Expected Result:**
- Products are reordered from lowest price to highest price.

## TC-PB-06: Sort Products by Name (A–Z)

**Steps:**
1. Open the website homepage.
2. Navigate to a category (e.g., Apparel & Shoes).
3. Select Name: A–Z from the sorting dropdown.

**Expected Result:**
- Products are sorted alphabetically by product name.


# Product Details Page (PDP)


## TC-PDP-07: Verify Product Details Page Loads Successfully

**Steps:**
1. Open the website homepage.
2. Navigate to any category.
3. Click on a product image or product name.

**Expected Result:**
- The Product Details Page loads without errors.
- The correct product page is displayed.

## TC-PDP-08: Verify User Can Select Product Attributes

**Preconditions:**
- The product has selectable attributes (e.g., size, color).

**Steps:**
1. Open the Product Details Page.
2. Select a different size (if available).
3. Select a different color (if available).

**Expected Result:**
- Selected attributes are applied correctly.
- No validation errors appear.

## TC-PDP-09: Add In-Stock Product to Cart from PDP

**Precondition:**
 Product is in stock.
 
**Steps:**
1. Open a product PDP.
2. Click the Add to Cart button.
   
**Expected Result:**
- Product is added to the cart.
- Confirmation message appears at the top of the page.

## TC-PDP-10: Out-of-Stock Product Does Not Allow Add to Cart

**Precondition:**
The product is out of stock.

**Steps:**
1. Open the product that is out of stock.

**Expected Result:**
- The " Add to Cart” button is disabled or hidden.
- “Out of stock” message is displayed.

## TC-PDP-11: Email a Friend Functionality

**Steps:**
1. Open any product PDP.
2. Click Email a Friend.
3. Enter valid email details.
4. Submit the form.
   
**Expected Result:**
- The email form is submitted successfully.
- Confirmation message is displayed.

  
# Wishlist Test Cases


## TC-WL-12: Add Product to Wishlist

**Steps:**
1. Open any product.
2. Click Add to Wishlist.
   
**Expected Result:**
- Product added to the wishlist.
- Confirmation message is displayed.

## TC-WL-13: Remove Product from Wishlist

**Precondition:** 
Product exists in the wishlist.

**Steps:**
1. Open the Wishlist page.
2. Remove a product from the wishlist.
   
**Expected Result:**
- Product is removed successfully.
- Wishlist updates accordingly.

## TC-WL-14: Add Product to Cart from Wishlist

**Precondition:**
 Product exists in the wishlist.
 
**Steps:**
1. Open the Wishlist page.
2. Click Add to Cart for a product.
   
**Expected Result:**
- Product is added to the cart.
- Cart icon updates item count.
- Product is removed from the wishlist.


# Shopping Cart Test Cases


## TC-CART-15: Change Product Quantity in Cart

**Steps:**
1. Add any product to the cart.
2. Open the Cart page.
3. Change the product quantity.
   
**Expected Result:**
- Product quantity updates successfully.
- Item total and cart subtotal update correctly.

## TC-CART-16: Apply Discount Coupon Code

**Precondition:**
Discount Coupon Code: TEST_V1

**Steps:**
1. Open the Cart page.
2. Enter a valid coupon code.
3. Click Apply.
   
**Expected Result:**
- The discount is applied correctly.
- Updated total is displayed.

## TC-CART-17: Remove Product from Cart

**Precondition:**
The product has already been added to the cart.

**Steps:**
1. Open the Cart page.
2. Remove a product from the cart.
   
**Expected Result:**
- Product is removed.
- Cart subtotal updates correctly.

## TC-CART-18: Proceed to Checkout from Cart Page

**Preconditions:**
At least one product is added to the shopping cart.

**Steps:**
1. Open the Cart page.
2. Select the checkbox “I agree with the terms of service and I adhere to them unconditionally”.
3. Click the Proceed to Checkout button.
   
**Expected Result:**
- The system allows the user to proceed.
- The user is redirected to the Checkout page.
- The checkout process starts successfully.

## TC-CART-19: Checkout Blocked Without Accepting Terms of Service

**Preconditions:**
At least one product is added to the shopping cart.

**Steps:**
1. Open the Cart page.
2. Do not select the “I agree with the terms of service” checkbox.
3. Click Proceed to Checkout.
   
**Expected Result:**
- User is not redirected to checkout.
- Validation message is displayed (e.g., “You must agree to the terms of service before proceeding.”).


# Cross-Browser Test Cases


## TC-CB-20: Verify Product Pages in Chrome and Safari

**Steps:**
1. Open the website in Chrome.
2. Navigate through homepage, category page, PDP, and cart.
3. Repeat the same steps in Safari.
   
**Expected Result:**
- Pages display correctly in both browsers.
- No layout issues, broken links, or missing elements.

## TC-CB-21: Add Product to Cart in Chrome and Safari

**Steps:**
1. Open the website in Chrome.
2. Add a product to the cart.
3. Open the website in Safari.
4. Add the same product to the cart.
   
**Expected Result:**
- The product has been successfully added to the cart in both browsers.
- Confirmation message appears.
- Cart item count updates correctly.


# Accessibility (A11y) Test Cases


## TC-A11Y-22: Keyboard Navigation on Product Pages

**Steps:**
1. Open the website homepage.
2. Navigate through categories and the PDP using Tab and Shift + Tab.
   
**Expected Result:**
- All interactive elements are reachable.
- A visible focus indicator is present.

## TC-A11Y-23: Product Images Have Alt Text

**Steps:**
1. Inspect product images using DevTools or a screen reader.
   
**Expected Result:**
- Product images contain meaningful alt text.

## TC-A11Y-24: Add Product to Cart Using Keyboard Only

**Steps:**
1. Open a product PDP.
2. Navigate to the Add to Cart button using the keyboard.
3. Press Enter.
   
**Expected Result:**
- The product has been added to the cart successfully.
- Confirmation message appears.

## TC-A11Y-25: Page Zoom at 200%

**Steps:**
1. Open the website homepage.
2. Zoom the page to 200%.
   
**Expected Result:**
- Page content remains readable.
- No content is cut off or overlaps.
- Horizontal scrolling is not required.

  



