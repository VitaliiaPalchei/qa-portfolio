 # Search Test Cases

 
## TC-SR-01: Search with Valid Keyword

**Steps:**
1. Open the website homepage.
2. Enter a valid keyword (e.g., book) in the search field.
3. Click the search.
   
**Expected Result:**
- Search Results page loads successfully.
- Products matching the entered keyword are displayed.

  
# Product Browsing (PLP – Product Listing Page)


## TC-PB-01: Verify Category Page Opens and Displays Product List

**Steps:**
1. Open the website homepage.
2. Click any category from the top navigation menu or side category list.
   
**Expected Result:**
- The selected category page opens successfully.
- A list of products is displayed.
- Each product appears as a separate product tile.

## TC-PB-02: Verify Product Tile Displays Required Elements

**Steps:**
1. Open the website homepage.
2. Click on any category page containing products.
   
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
2. Open any category (e.g., Books).
3. Click the Add to Cart button on a product tile.
   
**Expected Result:**
- Product is added to the cart
- Confirmation message appears.
- Cart icon updates the item count.

## TC-PB-04: Sort Products by Price (Low to High)

**Steps:**
1. Open the website homepage.
2. Click on any product category from the navigation menu.
3. Select Price: Low to High from the sorting dropdown.
   
**Expected Result:**
- Products are reordered from lowest price to highest price.

## TC-PB-05: Sort Products by Name (A–Z)

**Steps:**
1. Open the website homepage.
2. Click on any product category (e.g., Apparel & Shoes).
3. Select Name: A–Z from the sorting dropdown.
   
**Expected Result:**
- Products are sorted alphabetically by product name.


# Product Details Page (PDP)


## TC-PDP-01: Verify Product Details Page Loads Successfully

**Steps:**
1. Open the website homepage.
2. Select any product category.
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
 The user is not required to be logged in (guest checkout supported).
 
**Steps:**
1. Open the website homepage.
2. Click on any product category from the main menu.
3. Select an in-stock product by clicking on the product name or product image.
4. Click the Add to Cart button.
   
**Expected Result:**
- Product is added to the cart.
- Confirmation message appears at the top of the page.

## TC-PDP-03: Out-of-Stock Product Does Not Allow Add to Cart

**Precondition:**
The product is out of stock.

**Steps:**
1. Open the website homepage.
2. Navigate to a product category that contains out-of-stock items.
3. Select a product that is marked as out of stock.
   
**Expected Result:**
- The " Add to Cart” button is disabled or hidden.
- “Out of stock” message is displayed.

## TC-PDP-05: Email a Friend Functionality

**Steps:**
1. Open the website homepage.
2. Open any product from the homepage.
3. On the Product Details Page, click the Email a Friend button.
4. Enter a valid email address in the Friend’s Email field.
5. Enter a valid email address in the Your Email field.
6. Enter a message in the Personal Message text area.
7. Click the Send Email button.
   
**Expected Result:**
- The email form is submitted successfully.
- A confirmation message is displayed indicating that the email has been sent.
- No validation or system errors occur.


# Wishlist Test Cases


## TC-WL-01: Add Product to Wishlist

**Steps:**
1. Open the website homepage.
2. Open any product.
3. Click the 'Add to Wishlist' button.
   
**Expected Result:**
- Product added to the wishlist.
- Confirmation message is displayed.

## TC-WL-02: Remove Product from Wishlist

**Precondition:** 
The product has already been added to your wishlist.

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

