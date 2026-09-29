# 🧪 Mina Online Store — Add to Cart Testing

![DEPI](https://img.shields.io/badge/DEPI-Software%20Testing-blue)
![Testing](https://img.shields.io/badge/Testing-Manual%20Testing-green)
![ISTQB](https://img.shields.io/badge/ISTQB-v4.0-orange)
![Status](https://img.shields.io/badge/Project-Completed-success)

## DEPI – Software Testing Track

### Part 02: ISTQB – Static / Manual Testing (Task 2)

This project was completed as part of the **Digital Egypt Pioneers Initiative (DEPI) – Software Testing Track**.

The task focuses on testing the **Add Product to Cart** feature of Mina's Online Store from functional and non-functional perspectives.

---

# 🌐 Application Under Test

**Target Page:**

https://minayounan-cs.github.io/TestLab/products.html

**Feature Under Test:**

> Add Product to Cart

---

# 👤 1. User Scenario

As a visitor or logged-in customer of Mina's Online Store, I want to browse the available products and add one or more items to my shopping cart so that I can later review them and proceed to checkout.

---

# 📋 2. Functional Requirements

The Products page should:

* Display a grid of products.
* Display the product name.
* Display the price in Egyptian Pounds (ج.م).
* Display a visual representation such as an emoji or image.
* Provide an **"أضف إلى السلة"** button.

When the user clicks **"أضف إلى السلة"**:

1. The product should be added to the cart.
2. If the product is not already in the cart, its quantity should be `1`.
3. If the product already exists, its quantity should increase by `1`.
4. The cart badge should be updated immediately.
5. The button should provide temporary success feedback.
6. The cart should use `localStorage` for persistence.
7. The feature should work for both anonymous and logged-in users.

---

# ⚙️ 3. Non-Functional Requirements

## Usability

* The Add to Cart button should be clearly visible.
* The button should have the correct Arabic label.
* Feedback should appear within 1–2 seconds.

## Performance

* The Add to Cart operation should complete in less than 1 second under normal conditions.

## Reliability

* Cart information should remain available after refreshing the page.

## Compatibility

The feature should work on modern:

* Chrome
* Firefox
* Edge
* Safari

The layout should also remain usable on desktop and mobile screen sizes.

## Accessibility

* Buttons should be keyboard accessible.
* Text should have sufficient color contrast.
* Interactive elements should be clearly visible and usable.

---

# 🔄 4. Use Case

### Use Case ID

`UC-ADD-CART-01`

### Title

Add a product to the shopping cart

### Actor

Customer — Anonymous or Authenticated

### Preconditions

* User is on the Products page.
* At least one product is displayed.

### Main Flow

1. User opens the Products page.
2. User views the product grid.
3. User clicks **"أضف إلى السلة"**.
4. System adds the product to the cart.
5. System updates the cart badge.
6. System displays temporary success feedback.

### Postconditions

* The selected product appears in the cart.
* The product has the correct quantity.
* The cart badge displays the correct total quantity.

### Alternative / Exception Flow

* If the product already exists in the cart, its quantity is incremented.
* If localStorage is unavailable, the system should handle the situation gracefully without crashing.

---

# 🧪 5. Test Case Summary

| Test Case | Title                                             | Result |
| --------- | ------------------------------------------------- | ------ |
| TC-ADD-01 | Verify product cards are correctly rendered       | ✅ Pass |
| TC-ADD-02 | Verify adding a new product to the cart           | ✅ Pass |
| TC-ADD-03 | Verify adding the same product increases quantity | ✅ Pass |
| TC-ADD-04 | Verify cart badge shows total quantity            | ✅ Pass |
| TC-ADD-05 | Verify cart data remains after refresh            | ✅ Pass |
| TC-ADD-06 | Add product as anonymous user                     | ❌ Fail |
| TC-ADD-07 | Verify no JS errors for anonymous user            | ✅ Pass |
| TC-ADD-08 | Verify no JS errors for logged-in user            | ✅ Pass |
| TC-ADD-09 | Verify logged-in user can add product             | ✅ Pass |
| TC-ADD-10 | Verify responsive layout                          | ✅ Pass |
| TC-ADD-11 | Verify localStorage unavailability handling       | ❌ Fail |
| TC-ADD-12 | Verify Add to Cart with localStorage available    | ✅ Pass |
| TC-ADD-13 | Verify keyboard accessibility                     | ✅ Pass |
| TC-ADD-14 | Verify sufficient color contrast                  | ❌ Fail |
| TC-ADD-15 | Verify Add to Cart performance                    | ✅ Pass |
| TC-ADD-16 | Verify success feedback timing                    | ✅ Pass |

---

# 📊 6. Test Execution Results

| Metric                 |     Result |
| ---------------------- | ---------: |
| Total Test Cases       |         16 |
| Passed                 |         13 |
| Failed                 |          3 |
| Blocked                |          0 |
| Pass Rate              | **81.25%** |
| Exploratory Test Cases |          4 |
| Exploratory Findings   |          4 |

### Pass Rate Calculation

```text
Pass Rate = Passed Test Cases / Total Test Cases × 100

Pass Rate = 13 / 16 × 100

Pass Rate = 81.25%
```

---

# 📝 7. Detailed Test Cases

## TC-ADD-01 — Verify Product Cards Are Correctly Rendered

**Preconditions:**
User is on the Products page.

**Test Steps:**

1. Open the Products page.
2. View the product grid.
3. Inspect each visible product card.

**Test Data:**
Products page with available products.

**Expected Result:**

Each product card should display:

* Product name
* Price in Egyptian Pounds (ج.م)
* Visual representation
* "أضف إلى السلة" button

**Actual Result:**

Product cards displayed the required information.

**Status:** ✅ Pass

**Severity:** High
**Priority:** High

---

## TC-ADD-02 — Verify Adding a New Product to the Cart

**Preconditions:**

* Products page is opened.
* Cart is empty.

**Test Steps:**

1. Open the Products page.
2. Select a product.
3. Click **"أضف إلى السلة"**.

**Test Data:**

`هاتف ذكي سامسونج`

**Expected Result:**

* Product is added to the cart.
* Quantity is `1`.
* Cart badge increases by `1`.
* Button displays temporary success feedback.

**Actual Result:**

Product was added successfully with quantity `1`, the cart badge increased, and success feedback appeared.

**Status:** ✅ Pass

**Severity:** Medium
**Priority:** High

---

## TC-ADD-03 — Verify Adding the Same Product Again Increases Quantity

**Preconditions:**

* Products page is opened.
* Product already exists in the cart with quantity `1`.

**Test Steps:**

1. Open the Products page.
2. Select the product.
3. Click "أضف إلى السلة".
4. Click "أضف إلى السلة" again.
5. Open the cart.
6. Verify the product quantity.

**Test Data:**

`هاتف ذكي سامسونج`

**Expected Result:**

* Product quantity increases to `2`.
* Cart badge increases by `1`.
* Temporary success feedback appears.

**Actual Result:**

Product quantity increased to `2`, the cart badge was updated, and success feedback appeared.

**Status:** ✅ Pass

**Severity:** High
**Priority:** High

---

## TC-ADD-04 — Verify Cart Badge Shows Total Quantity

**Preconditions:**

Cart is empty.

**Test Steps:**

1. Add `هاتف ذكي سامسونج`.
2. Add the same product again.

**Test Data:**

`هاتف ذكي سامسونج × 2`

**Expected Result:**

Cart badge displays `2`.

**Actual Result:**

Cart badge displayed `2`.

**Status:** ✅ Pass

**Severity:** High
**Priority:** High

---

## TC-ADD-05 — Verify Cart Data Remains After Refresh

**Preconditions:**

A product already exists in the cart.

**Test Steps:**

1. Add a product to the cart.
2. Refresh the page.
3. Check the cart badge.
4. Check the cart contents.

**Expected Result:**

* Product remains in the cart.
* Cart badge shows the same quantity.
* Cart data remains stored in localStorage.

**Actual Result:**

Product remained in the cart and the cart data persisted after refresh.

**Status:** ✅ Pass

**Severity:** High
**Priority:** High

---

## TC-ADD-06 — Add Product to Cart as Anonymous User

**Preconditions:**

User is not logged in.

**Test Steps:**

1. Open the Products page.
2. Click any product.
3. Click "أضف إلى السلة".

**Test Data:**

Any product.

**Expected Result:**

* Product is added successfully.
* Cart badge is updated.

**Actual Result:**

The application displayed:

> "يجب تسجيل الدخول أولاً لإضافة منتجات إلى السلة"

The product was not added for the anonymous user.

**Status:** ❌ Fail

**Severity:** High
**Priority:** High

**Defect:** `DEF-ADD-01`

---

## TC-ADD-07 — Verify No JavaScript Errors for Anonymous User

**Preconditions:**

User is not logged in.

**Test Steps:**

1. Open the Products page.
2. Click "أضف إلى السلة".
3. Open the browser Console.
4. Check for JavaScript errors.

**Expected Result:**

No JavaScript errors should occur.

**Actual Result:**

No JavaScript errors were observed.

**Status:** ✅ Pass

**Severity:** Low
**Priority:** Medium

---

## TC-ADD-08 — Verify No JavaScript Errors for Logged-in User

**Preconditions:**

User is logged in.

**Test Steps:**

1. Open the Products page.
2. Click "أضف إلى السلة".
3. Open the browser Console.
4. Check for JavaScript errors.

**Expected Result:**

No JavaScript errors should occur.

**Actual Result:**

No JavaScript errors were observed.

**Status:** ✅ Pass

**Severity:** Low
**Priority:** Medium

---

## TC-ADD-09 — Verify Logged-in User Can Add a Product

**Preconditions:**

User is logged in and is on the Products page.

**Test Steps:**

1. Open Products page.
2. Select a product.
3. Click "أضف إلى السلة".
4. Open the cart.

**Expected Result:**

* Product is added.
* Quantity is `1`.
* Cart badge is updated.
* Temporary success feedback appears.

**Actual Result:**

Product was added successfully with the expected quantity and feedback.

**Status:** ✅ Pass

**Severity:** High
**Priority:** High

---

## TC-ADD-10 — Verify Responsive Layout

**Preconditions:**

Products page is opened.

**Test Steps:**

1. Open the Products page on desktop.
2. Change the browser viewport to a mobile size.
3. Verify product cards and buttons.

**Expected Result:**

* Layout is responsive.
* Product cards remain readable.
* Buttons remain visible and clickable.

**Actual Result:**

The layout remained usable on desktop and mobile viewports.

**Status:** ✅ Pass

**Severity:** Low
**Priority:** Medium

---

## TC-ADD-11 — Verify localStorage Unavailability Is Handled Gracefully

**Preconditions:**

* User is on the Products page.
* localStorage is unavailable or blocked.

**Test Steps:**

1. Disable/block localStorage.
2. Click "أضف إلى السلة".
3. Observe system behavior.
4. Check browser Console.

**Expected Result:**

The system should handle localStorage unavailability gracefully without crashing or displaying JavaScript errors.

**Actual Result:**

The browser Console displayed:

```text
Uncaught Error: localStorage disabled
```

The error occurred in:

```text
saveCart() at app.js:39
```

called from:

```text
addToCart() at app.js:220
```

**Status:** ❌ Fail

**Severity:** Medium
**Priority:** High

**Defect:** `DEF-ADD-02`

---

## TC-ADD-12 — Verify Add to Cart When localStorage Is Available

**Preconditions:**

User is on the Products page and localStorage is available.

**Test Steps:**

1. Open the Products page.
2. Click "أضف إلى السلة".
3. Check the cart badge.
4. Verify the product in localStorage.

**Expected Result:**

* Product is added with quantity `1`.
* Cart badge is updated.
* Cart data is saved.
* No JavaScript errors occur.

**Actual Result:**

Product was added successfully, the badge was updated, and localStorage worked correctly.

**Status:** ✅ Pass

**Severity:** Low
**Priority:** High

---

## TC-ADD-13 — Verify Add to Cart Button Is Keyboard Accessible

**Preconditions:**

User is on the Products page.

**Test Steps:**

1. Open the Products page.
2. Press Tab until an Add to Cart button receives focus.
3. Press Enter.
4. Verify the result.

**Expected Result:**

The button should receive keyboard focus and be activatable using the keyboard.

**Actual Result:**

The button received focus using Tab and was successfully activated using Enter.

**Status:** ✅ Pass

**Severity:** Medium
**Priority:** High

---

## TC-ADD-14 — Verify Sufficient Color Contrast

**Preconditions:**

User is on the Products page.

**Test Steps:**

1. Open Chrome DevTools.
2. Open Lighthouse.
3. Select Accessibility.
4. Select Mobile.
5. Run the analysis.
6. Check the Contrast section.

**Expected Result:**

Foreground and background colors should have sufficient contrast.

**Actual Result:**

Lighthouse reported:

> Background and foreground colors do not have a sufficient contrast ratio.

**Lighthouse Accessibility Score:** `83`

**Status:** ❌ Fail

**Severity:** Medium
**Priority:** Medium

**Defect:** `DEF-ADD-03`

---

## TC-ADD-15 — Verify Add to Cart Completes Within 1 Second

**Preconditions:**

* User is on the Products page.
* localStorage is available.

**Test Steps:**

1. Open the Products page.
2. Click "أضف إلى السلة".
3. Measure the action and UI update time.
4. Repeat three times.

**Expected Result:**

The operation should complete in less than `1 second`.

**Actual Result:**

Measured times:

```text
6.20 ms
1.00 ms
0.90 ms
```

All measurements were below `1 second`.

**Status:** ✅ Pass

**Severity:** Medium
**Priority:** High

**Measurement Tool:**

`performance.now()`

---

## TC-ADD-16 — Verify Success Feedback Is Displayed Promptly

**Preconditions:**

User is on the Products page.

**Test Steps:**

1. Open the Products page.
2. Click "أضف إلى السلة".
3. Observe the button feedback.

**Expected Result:**

Temporary success feedback should appear within `1–2 seconds`.

**Actual Result:**

The **"تم الإضافة"** feedback appeared immediately after clicking the button.

**Status:** ✅ Pass

**Severity:** Medium
**Priority:** Medium

---

# 🔎 8. Exploratory Testing

In addition to the predefined test cases, exploratory testing was performed to investigate additional behaviors and potential risks.

> Exploratory findings are reported separately because some scenarios require clarification of the expected business behavior.

---

## ETC-01 — Verify Product Stock and Availability Handling

**Preconditions:**

User is on the Products page.

**Test Steps:**

1. Check available stock for a product.
2. Try adding a product while stock is available.
3. Try reaching/exceeding the available quantity.
4. Check behavior when the product becomes unavailable.

**Expected Result:**

The system should clearly indicate product availability and prevent adding products when stock is exhausted.

**Actual Result:**

Stock quantity and out-of-stock behavior were not clearly defined or displayed in the tested flow.

**Status:** ❌ Finding

**Severity:** Medium
**Priority:** Medium

**Observation:**

Stock and availability requirements need clarification.

---

## ETC-02 — Verify Full Name Validation

**Preconditions:**

User is on a form containing the Full Name field.

**Test Steps:**

1. Enter one character.
2. Submit the form.
3. Enter a name with more than one character.
4. Submit again.

**Expected Result:**

The system should apply appropriate validation rules to the Full Name field.

**Actual Result:**

The system accepted a single-character name and also accepted names containing more than one character.

**Status:** ❌ Finding

**Severity:** Low
**Priority:** Medium

**Observation:**

The minimum length requirement for Full Name is not clearly specified.

---

## ETC-03 — Verify Password Protection During Excel Export

**Preconditions:**

User information has been entered and an Excel export option is available.

**Test Steps:**

1. Enter a password.
2. Export the data to Excel.
3. Open the exported Excel file.
4. Check the password field.

**Expected Result:**

Passwords should not be exposed in plain text in the exported file.

**Actual Result:**

The password appeared in plain text in the exported Excel file.

**Status:** ❌ Finding

**Severity:** High
**Priority:** High

**Observation:**

Sensitive password information is exposed in the exported Excel file.

---

## ETC-04 — Verify Cart Behavior After Completing an Order Without Payment

**Preconditions:**

A product has been added to the cart and the user can proceed to order completion.

**Test Steps:**

1. Add a product to the cart.
2. Proceed to checkout/order completion.
3. Complete the order without making a real payment.
4. Return to the cart.

**Expected Result:**

The system should clearly handle the order state and should not unexpectedly remove cart items before a valid order/payment process is completed.

**Actual Result:**

The cart became empty after completing the order without payment.

**Status:** ❌ Finding

**Severity:** Medium
**Priority:** Medium

**Observation:**

Expected cart behavior after an unpaid order requires clarification.

---

# ☑️ 9. Feature Checklist

| Checklist Item                                   | Result |
| ------------------------------------------------ | ------ |
| Product cards correctly rendered                 | ✅ Pass |
| Add to Cart button present and correctly labeled | ✅ Pass |
| Button clickable/enabled                         | ✅ Pass |
| Cart badge updates immediately                   | ✅ Pass |
| Same product increases quantity                  | ✅ Pass |
| Visual feedback appears                          | ✅ Pass |
| Cart persists after refresh                      | ✅ Pass |
| Anonymous user can add product                   | ❌ Fail |
| Logged-in user can add product                   | ✅ Pass |
| No JavaScript errors                             | ✅ Pass |
| localStorage errors handled gracefully           | ❌ Fail |
| Add to Cart completes within 1 second            | ✅ Pass |
| Success feedback within 1–2 seconds              | ✅ Pass |
| Keyboard accessibility                           | ✅ Pass |
| Sufficient color contrast                        | ❌ Fail |
| Desktop/mobile layout                            | ✅ Pass |

---

# 🐞 10. Confirmed Defects

## DEF-ADD-01 — Anonymous Users Cannot Add Products

**Severity:** High
**Priority:** High
**Status:** Open
**Related Test Case:** `TC-ADD-06`

### Description

Anonymous users cannot add products to the cart.

Instead, the application displays:

```text
يجب تسجيل الدخول أولاً لإضافة منتجات إلى السلة
```

### Expected

Anonymous users should be able to add products according to the provided requirement.

### Actual

The application requires the user to log in before adding a product.

---

## DEF-ADD-02 — localStorage Unavailability Is Not Handled Gracefully

**Severity:** Medium
**Priority:** High
**Status:** Open
**Related Test Case:** `TC-ADD-11`

### Description

The application throws a JavaScript error when localStorage is unavailable.

### Observed Error

```text
Uncaught Error: localStorage disabled
```

### Location

```text
saveCart() → app.js:39
addToCart() → app.js:220
```

---

## DEF-ADD-03 — Insufficient Color Contrast

**Severity:** Medium
**Priority:** Medium
**Status:** Open
**Related Test Case:** `TC-ADD-14`

### Description

Lighthouse identified insufficient foreground/background color contrast.

### Evidence

Lighthouse Accessibility Score:

```text
83
```

---

# 🔎 11. Exploratory Findings

| ID         | Finding                                                          | Severity | Related Test |
| ---------- | ---------------------------------------------------------------- | -------- | ------------ |
| DEF-EXP-01 | Stock/availability behavior is unclear                           | Medium   | ETC-01       |
| DEF-EXP-02 | Full Name minimum length is unclear                              | Low      | ETC-02       |
| DEF-EXP-03 | Password exposed in plain text during Excel export               | High     | ETC-03       |
| DEF-EXP-04 | Cart becomes empty after unpaid order; expected behavior unclear | Medium   | ETC-04       |

### Important Distinction

The project contains:

**3 confirmed defects** from the predefined Add to Cart test cases.

Additionally, **4 exploratory findings** were identified during exploratory testing.

Therefore:

```text
Confirmed Add-to-Cart Defects = 3
Exploratory Findings = 4
Total Findings = 7
```

The four exploratory findings should not all be treated as confirmed defects without clarifying the relevant requirements.

---

# ⚡ 12. Performance Testing Evidence

The Add to Cart operation was measured using the browser `performance.now()` API.

| Execution |    Time |
| --------- | ------: |
| Run 1     | 6.20 ms |
| Run 2     | 1.00 ms |
| Run 3     | 0.90 ms |

### Requirement

`< 1 second`

### Result

✅ **Pass**

All measured execution times were significantly below the defined threshold.

---

# ♿ 13. Accessibility Testing

Accessibility testing included:

* Keyboard navigation
* Keyboard activation
* Button focus
* Color contrast analysis
* Lighthouse accessibility audit

### Results

**Keyboard Accessibility:** ✅ Pass

**Color Contrast:** ❌ Fail

**Lighthouse Accessibility Score:** `83`

---

# 📱 14. Responsive Testing

The Products page was checked on:

* Desktop viewport
* Mobile viewport

### Result

✅ **Pass**

Product cards remained readable and Add to Cart buttons remained visible and usable.

---

# 🌐 15. Compatibility Testing

The requirements specified support for modern desktop and mobile browsers:

* Google Chrome
* Mozilla Firefox
* Microsoft Edge
* Safari

The testing scope included cross-browser compatibility as a non-functional requirement.

---

# 🛠️ 16. Testing Tools

| Tool                | Usage                            |
| ------------------- | -------------------------------- |
| Chrome DevTools     | Browser inspection and debugging |
| Chrome Console      | JavaScript error detection       |
| Lighthouse          | Accessibility analysis           |
| `performance.now()` | Performance measurement          |
| localStorage        | Cart persistence validation      |
| Microsoft Word      | Test documentation               |
| Microsoft Excel     | Test case documentation          |
| PDF                 | Test execution report            |
| Git                 | Version control                  |
| GitHub              | Project repository               |

---

# 📂 17. Project Artifacts

The repository contains the testing documentation created for this task.

```text
Mina-Online-Store-Testing/
│
├── README.md
│
├── File 1.docx
│
├── Mina-Online-Store-Testing.docx
│
└── Test Report
    (Mahmoud Bakri, Naswa Nassar,
     Manar Galal, Ahmed Ramzy).pdf
```

### Documentation Includes

* Requirements analysis
* Test cases
* Test execution results
* Exploratory testing
* Checklist
* Defect identification
* Performance testing
* Accessibility testing
* Test execution report

---

# 📈 18. Testing Process

The testing workflow followed this general process:

```text
Requirements Analysis
        ↓
Test Scenario Identification
        ↓
Test Case Design
        ↓
Test Data Preparation
        ↓
Manual Test Execution
        ↓
Exploratory Testing
        ↓
Defect Identification
        ↓
Evidence Collection
        ↓
Result Analysis
        ↓
Test Report
```

---

# 👥 19. Test Team

* **Mahmoud Bakri**
* **Naswa Nassar**
* **Manar Galal**
* **Ahmed Ramzy**

---

# 🎓 20. Training Information

**Program:** Digital Egypt Pioneers Initiative (DEPI)

**Track:** Software Testing

**Part:** Part 02 – ISTQB: Static / Manual Testing

**Task:** Task 2

**Instructor:** Mina Younan

**Instructor Email:** [mina.younan@mu.edu.eg](mailto:mina.younan@mu.edu.eg)

---

# 📅 21. Test Execution Information

**Test Date:** 15 September 2026

**Environment:**

* Browser: Google Chrome
* Operating System: Windows 10

**Application:**

https://minayounan-cs.github.io/TestLab/products.html

---

# 📌 22. Final Summary

The Add to Cart feature was evaluated through **16 predefined test cases** covering functional behavior, reliability, usability, accessibility, performance, compatibility, and error handling.

### Final Results

```text
16 Test Cases Executed
13 Passed
3 Failed
0 Blocked
81.25% Pass Rate
```

Three confirmed defects were identified:

1. Anonymous users cannot add products.
2. localStorage unavailability is not handled gracefully.
3. Insufficient color contrast was identified by Lighthouse.

Four additional exploratory findings were identified involving:

* Product stock and availability
* Full Name validation
* Password exposure during Excel export
* Cart behavior after an unpaid order

The project demonstrates practical experience in **manual testing, test case design, exploratory testing, defect reporting, browser debugging, accessibility testing, performance testing, and test documentation**.

---

# 🔗 Application Under Test

**Mina's Online Store**

https://minayounan-cs.github.io/TestLab/products.html

---

# 👨‍💻 Author

## Mahmoud Bakri

**Software Testing Engineer Trainee | DEPI**

### GitHub

https://github.com/MahmoudBakri225/

### LinkedIn

https://linkedin.com/in/mahmoud-bakri-swt/
