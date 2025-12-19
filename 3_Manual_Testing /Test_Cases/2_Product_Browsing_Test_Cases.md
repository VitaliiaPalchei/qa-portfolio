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


## TC-PB-01: Verify Category Page Opens and Displays Product List

**Steps:**
1. Open the website homepage.
2. Click any product category from the top navigation menu or side category list.
**Expected Result:**
- The selected category page opens successfully.
- A list of products is displayed.
- Each product appears as a separate product tile.

## TC-PB-02: Verify Product Tile Displays Required Elements

**Steps:**
1. Open the website homepage.
2. Navigate to any category page containing products.
**Expected Result:**
- Each product tile displays:
             Product image
             Product name
             Product price
             Rating stars 
             Add to Cart button
  
## TC-PB-03: Add Product to Cart from Product Listing Page

**Steps:**
1. Open the website homepage.
2. Navigate to any category (e.g., Books).
3. Click the Add to Cart button on a product tile.
**Expected Result:**
- Product is added to the cart
- Confirmation message appears.
- Cart icon updates the item count.
- User remains on the category page.

## TC-PB-04: Sort Products by Price (Low to High)

**Steps:**
1. Open the website homepage.
2. Navigate to any product category.
3. Select Price: Low to High from the sorting dropdown.
**Expected Result:**
- Products are reordered from lowest price to highest price.

## TC-PB-05: Sort Products by Name (A–Z)

**Steps:**
1. Open the website homepage.
2. Navigate to a category (e.g., Apparel & Shoes).
3. Select Name: A–Z from the sorting dropdown.
**Expected Result:**
- Products are sorted alphabetically by product name.


# Product Details Page (PDP)


## TC-PDP-01: Verify Product Details Page Loads Successfully
**Steps:**
1. Open the website homepage.
2. Navigate to any category.
3. Click on a product image or product name.
**Expected Result:**
- The Product Details Page loads without errors.
- The correct product page is displayed.

## TC-PDP-04: Verify User Can Select Product Attributes

**Preconditions:**
- The product has selectable attributes (e.g., size, color).
**Steps:**
1. Open the Product Details Page.
2. Select a different size (if available).
3. Select a different color (if available).
**Expected Result:**
- Selected attributes are applied correctly.
- No validation errors appear.

## TC-PDP-02: Add In-Stock Product to Cart from PDP

**Precondition:**
 Product is in stock.
**Steps:**
1. Open a product PDP.
2. Click the Add to Cart button.
**Expected Result:**
- Product is added to the cart.
- Confirmation message appears at the top of the page.

## TC-PDP-03: Out-of-Stock Product Does Not Allow Add to Cart

**Precondition:**
The product is out of stock.
**Steps:**
1. Open the product that is out of stock.
**Expected Result:**
- The " Add to Cart” button is disabled or hidden.
- “Out of stock” message is displayed.

## TC-PDP-05: Email a Friend Functionality

**Steps:**
1. Open any product.
2. Click Email a Friend.
3. Enter valid email details.
4. Submit the form.
**Expected Result:**
- The email form is submitted successfully.
- Confirmation message is displayed.


# Wishlist Test Cases


## TC-WL-01: Add Product to Wishlist

**Steps:**
1. Open any product.
2. Click Add to Wishlist.
**Expected Result:**
- Product added to the wishlist.
- Confirmation message is displayed.

## TC-WL-02: Remove Product from Wishlist

**Precondition:** 
Product exists in the wishlist.
**Steps:**
1. Open the Wishlist page.
2. Remove a product from the wishlist.
**Expected Result:**
- Product is removed successfully.
- Wishlist updates accordingly.

## TC-WL-03: Add Product to Cart from Wishlist

**Precondition:**
 Product exists in the wishlist.
**Steps:**
1. Open the Wishlist page.
2. Click Add to Cart for a product.
**Expected Result:**
- Product is added to the cart.
- Cart icon updates item count.
- Product is removed from the wishlist.

