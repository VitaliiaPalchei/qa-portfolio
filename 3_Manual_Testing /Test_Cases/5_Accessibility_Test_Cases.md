
## TC-A11Y-00: Create Account Page Using Keyboard Only

**Steps:**
1. Open the Register Account page using the tab key.
2. Inspect all input fields (First Name, Last Name, Email, Password, Confirm Password) for associated labels.
3. Navigate through all form fields, checkboxes, and buttons using Tab.
4. Attempt to submit the form with keyboard only.

**Expected Result:**
- All input fields have proper labels.
- All interactive elements (fields, checkboxes, buttons) are reachable via keyboard navigation.
- Focus order is logical and sequential.
- Error messages, if triggered, are accessible to screen readers.

## TC-A11Y-01: Keyboard Navigation on Product Pages

**Steps:**
1. Open the website homepage.
2. Navigate through categories, product listing pages, and product details pages using only Tab and Shift + Tab keys.
3. Attempt to access interactive elements such as buttons, links, dropdowns, and checkboxes.
   
**Expected Result:**
- All interactive elements are reachable using the keyboard.
- A visible focus indicator is present on the selected element.

## TC-A11Y-02: Product Images Have Alt Text

**Steps:**
1. Open the website homepage.
2. Inspect product images using a screen reader or browser DevTools.
   
**Expected Result:**
- All product images contain meaningful alt text that describes the image.
- Each image product has been described by a screen reader.

## TC-A11Y-03: Add Product to Cart Using Keyboard Only

**Steps:**
1. Open a product details page (PDP).
2. Navigate to the “Add to Cart” button using only the keyboard.
3. Press Enter to add the product.
   
**Expected Result:**
- The product is added to the cart successfully.
- A confirmation message appears.

## TC-A11Y-04: Page Zoom Functionality

**Steps:**
1. Open the website homepage.
2. Zoom the page to 200% using browser zoom.
3. Navigate and interact with the page using keyboard and mouse.
   
**Expected Result:**
- All page content remains visible and readable.
- No content is cut off or hidden.

## TC-A11Y-05: Form Field Labels

**Steps:**
1. Open pages with forms (Registration, Login, Checkout).
2. Inspect all form fields using DevTools or a screen reader.
   
**Expected Result:**
- Each form field has an associated label.
- Labels are properly linked to their corresponding input fields.

## TC-A11Y-06: Color Contrast

**Steps:**
1. Open key pages (homepage, product pages, checkout).
2. Use a color contrast analyzer tool or inspect manually.

**Expected Result:**
- Text and interactive elements meet WCAG 2.1 AA minimum contrast standards.
- Text is readable for visually impaired users.

## TC-A11Y-07: Focus Order and Logical Navigation

**Steps:**
1. Open any page with interactive elements.
2. Navigate sequentially through the page using the Tab key.

**Expected Result:**
- Focus moves in a logical order corresponding to the page layout.
- No elements are skipped or inaccessible via keyboard navigation.

## TC-A11Y-08: Accessible Links and Buttons

**Steps:**
1. Open pages containing links and buttons.
2. Inspect or navigate using a screen reader or keyboard.

**Expected Result:**
- All clickable elements have meaningful labels or text.
- Screen readers announce each button or link appropriately.


