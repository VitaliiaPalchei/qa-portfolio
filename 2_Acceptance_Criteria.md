# Acceptance Criteria — Demo Web Shop


## 1. User Account Requirements

### 1.1 Registration

**AC1:** Required field validation
All required fields (First Name, Last Name, Email, Password, Confirm Password) must show validation messages when submitted empty.

**AC2:** First and last name validation
Names accept only valid characters.
Minimum and maximum length rules are enforced.
Invalid characters (numbers, special symbols) show an error message.

**AC3:** Email validation
Email must follow a valid format.
Duplicate (already registered) email is not allowed.
An error message is displayed for invalid or duplicate emails.

**AC4:** Password validation
Password must meet minimum length and complexity rules.
Password and Confirm Password must match.
Error messages appear when passwords are invalid or mismatched.
Password visibility toggle works correctly.

**AC5:** Successful registration behavior
User is successfully registered with valid data.
The user is redirected to the homepage or the account page after registration.

### 1.2 Login

**AC1:** Valid login
The user can log in with a valid email and password.

**AC2:** Invalid login handling
Logging in with invalid credentials shows a generic error message.

**AC3:** Remember Me functionality
“Remember Me” keeps the user logged in after a browser refresh.

**AC4:** Forgot password flow
“Forgot password” link navigates to reset flow.
The password reset email is sent, and the reset link works correctly.

**AC5:** Post-login behavior
The user is redirected to the homepage or account dashboard after logging in.

### 1.3 Logout

**AC1:** Logout functionality
Clicking “Logout” immediately ends the user session.

**AC2:** Post-logout behavior
The user is redirected to the homepage or the login page.
“Login” link becomes visible again.

## 2. Product Browsing Requirements

### 2.1 Category Browsing

**AC1:** Category navigation
Opening any category displays a list of products.
Empty categories show a “No products found” message.

### 2.2 Sorting & Filtering

**AC1:** Sorting
Sorting options reorder products correctly.

**AC2:** Display per page
Display-per-page options update the number of visible products.

**AC3:** View mode
Grid/List view toggle switches layout correctly.

### 2.3 Product Details Page (PDP)

**AC1:** PDP content
PDP displays product image, name, price, description, and reviews (if available).

**AC2:** PDP actions
“Add to Cart” is visible for in-stock products.
Out-of-stock products show an appropriate status and disable purchase.
Wishlist, Compare, and “Email a Friend” options are available.

## 3. Wishlist Requirements

**AC1:** Add to wishlist
Product can be added to the wishlist from PDP.

**AC2:** Wishlist management
Wishlist displays all added items.
“Update Wishlist” correctly saves changes.

**AC3:** Wishlist actions
Products can be added to the cart from the wishlist.
Wishlist can be shared.

## 4. Search Requirements

**AC1:** Valid search
Searching with a valid keyword returns matching products.

**AC2:** Empty search
Empty search shows a helpful warning message.

**AC3:** Invalid search
Searching for non-existent products shows “No results found”.

## 5. Shopping Cart Requirements

### 5.1 Add to Cart

**AC1:** Add product to cart
Clicking “Add to Cart” successfully adds the product.

**AC2:** Cart indicator
The cart icon updates the item count immediately.

**AC3:** Confirmation message
A notification confirms the product was added to the cart.

### 5.2 Cart Page

**AC1:** Cart contents
The cart displays the product name, image, price, quantity, and total.

**AC2:** Quantity update
Changing quantity updates the subtotal and total automatically.

**AC3:** Remove item
Removing an item updates the cart correctly.

**AC4:** Additional cart features
Discount code, gift card, and shipping estimator work correctly.
“I agree with the terms.” A checkbox is required to proceed to the checkout.

## 6. Checkout Requirements

**AC1:** Checkout navigation
Clicking “Proceed to Checkout” opens the checkout flow.

**AC2:** Checkout steps
Billing, shipping, payment, and confirmation steps load correctly.

**AC3:** Order placement
The order can be placed successfully with the required valid data.

**AC4:** Order confirmation
The confirmation page displays order details after successful checkout.

## 7. UI / UX Requirements

**AC1:** Layout consistency
Header, footer, and navigation appear on all pages.

**AC2:** Interactive elements
All buttons and links are clickable and functional.

**AC3:** Cross-browser support
Site displays correctly in Chrome and Safari (desktop).

## 8. Accessibility Requirements

**AC1:** Form accessibility
All form fields have associated labels.

**AC2:** Keyboard navigation
The entire site is usable with a keyboard only.

**AC3:** Visual accessibility
Text contrast meets WCAG minimum requirements.

**AC4:** Image accessibility
Product images contain meaningful alt text.

