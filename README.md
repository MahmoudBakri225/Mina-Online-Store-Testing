# 🧪 Mina Online Store — Add to Cart Testing

## DEPI – Software Testing Track

### Part 02: ISTQB – Static / Manual Testing (Task 2)

This project was completed as part of the **Digital Egypt Pioneers Initiative (DEPI)** Software Testing Track.

The task focuses on testing the **Add Product to Cart** feature of Mina's Online Store from both functional and non-functional perspectives.

---

## 🌐 Application Under Test

**Target Page:**
https://minayounan-cs.github.io/TestLab/products.html

**Feature Under Test:**
**Add Product to Cart**

### User Scenario

As a visitor or logged-in customer, the user should be able to browse available products and add one or more products to the shopping cart for later review and checkout.

---

## 🎯 Testing Objectives

The main objectives of this task were to verify that:

* Products are displayed correctly.
* Users can add products to the cart.
* Adding a new product sets its quantity to `1`.
* Adding the same product again increases its quantity.
* The cart badge displays the total quantity of all products.
* Cart data persists after refreshing the page.
* The feature works for anonymous and authenticated users.
* The system provides appropriate feedback after adding a product.
* The feature performs without noticeable delay.
* The feature is usable and accessible.
* The feature works across supported browsers and screen sizes.
* The application handles localStorage-related scenarios appropriately.

---

## 📋 Testing Scope

### Functional Testing

* Product display
* Add product to cart
* Add the same product multiple times
* Cart quantity calculation
* Cart badge update
* Cart persistence

### Non-Functional Testing

* Usability
* Performance
* Accessibility
* Compatibility
* Reliability

### Exploratory Testing

Additional scenarios were explored beyond the predefined functional requirements to identify unexpected behavior and unclear requirements.

---

## 🧪 Test Execution Summary

| Metric           |     Result |
| ---------------- | ---------: |
| Total Test Cases |         16 |
| Passed           |         13 |
| Failed           |          3 |
| Blocked          |          0 |
| Pass Rate        | **81.25%** |

### Result

**13 out of 16 test cases passed successfully.**

The three failed test cases resulted in confirmed defects that were documented separately.

---

## 🐞 Confirmed Defects

### DEF-ADD-01 — Anonymous Users Cannot Add Products

**Severity:** High
**Status:** Open

**Description:**
Anonymous users are unable to add products to the cart because the application requires the user to log in.

**Expected Result:**
According to the requirement, the Add to Cart feature should work for both anonymous and logged-in users.

**Actual Result:**
The user is required to log in before adding a product.

**Related Test Case:**
`TC-ADD-06`

---

### DEF-ADD-02 — localStorage Failure Is Not Handled Gracefully

**Severity:** Medium
**Status:** Open

**Description:**
When browser localStorage is unavailable or disabled, the application throws an error instead of providing appropriate handling.

**Observed Error:**

```text
Uncaught Error: localStorage disabled
```

**Expected Result:**
The application should gracefully handle the situation and provide an appropriate user-facing message or fallback behavior.

**Actual Result:**
A JavaScript error is thrown from the cart storage functionality.

**Related Test Case:**
`TC-ADD-11`

---

### DEF-ADD-03 — Insufficient Color Contrast

**Severity:** Medium
**Status:** Open

**Description:**
Accessibility analysis identified insufficient color contrast for some elements.

**Expected Result:**
Text and interactive elements should provide sufficient contrast according to accessibility guidelines.

**Actual Result:**
The Lighthouse accessibility audit reported a contrast issue.

**Lighthouse Accessibility Score:** `83`

**Related Test Case:**
`TC-ADD-14`

---

## 🔍 Exploratory Testing Findings

During exploratory testing, additional behaviors and requirement ambiguities were identified.

| ID         | Finding                                                 | Severity |
| ---------- | ------------------------------------------------------- | -------- |
| DEF-EXP-01 | Stock availability behavior is unclear                  | Medium   |
| DEF-EXP-02 | Full Name minimum length validation is unclear          | Low      |
| DEF-EXP-03 | Password is exposed as plain text during Excel export   | High     |
| DEF-EXP-04 | Cart behavior after an order without payment is unclear | Medium   |

> These exploratory findings were documented separately from the three confirmed Add-to-Cart defects because some require clarification of the expected business behavior.

---

## ⚡ Performance Testing

The Add to Cart operation was measured using browser developer tools.

Sample execution times:

* `6.20 ms`
* `1.00 ms`
* `0.90 ms`

### Expected Requirement

The Add to Cart action should complete in less than **1 second** under normal conditions.

### Result

**PASS**

The observed execution times were significantly below the defined threshold.

---

## ♿ Accessibility Testing

Accessibility was evaluated using **Lighthouse** and manual keyboard testing.

### Checks Included

* Keyboard focus
* Interactive element accessibility
* Button visibility
* Text readability
* Color contrast

### Result

Keyboard accessibility passed, while a color contrast issue was identified.

**Lighthouse Accessibility Score: 83**

---

## 🌐 Compatibility Testing

The feature was evaluated with consideration for modern desktop and mobile browsers.

### Target Browsers

* Google Chrome
* Mozilla Firefox
* Microsoft Edge
* Safari

Responsive behavior was also checked on desktop and mobile screen sizes.

---

## 🛠️ Tools Used

| Tool            | Purpose                                   |
| --------------- | ----------------------------------------- |
| Chrome DevTools | Browser inspection and debugging          |
| Lighthouse      | Accessibility and performance auditing    |
| Browser Console | JavaScript error detection                |
| LocalStorage    | Cart persistence verification             |
| Microsoft Excel | Test case documentation                   |
| PDF Reports     | Test execution and defect documentation   |
| Git & GitHub    | Version control and project documentation |

---

## 📁 Project Artifacts

The repository contains the testing documentation produced during the task.

```text
Mina-Online-Store-Testing/
│
├── README.md
│
├── File 1.docx
├── Mina-Online-Store-Testing.docx
└── Test Report (Mahmoud Bakri, Naswa Nassar, Manar Galal, Ahmed Ramzy).pdf
```

The documents contain the detailed test scenarios, test execution results, and testing report.

---

## 📊 Testing Approach

The testing process followed a structured approach:

```text
Requirements
     ↓
Test Scenario Identification
     ↓
Test Case Design
     ↓
Manual Test Execution
     ↓
Exploratory Testing
     ↓
Defect Identification
     ↓
Defect Documentation
     ↓
Test Result Analysis
     ↓
Test Report
```

---

## 👥 Test Team

* **Mahmoud Bakri**
* **Naswa Nassar**
* **Manar Galal**
* **Ahmed Ramzy**

---

## 🎓 Training Context

**Program:** Digital Egypt Pioneers Initiative (DEPI)
**Track:** Software Testing
**Task:** Part 02 – ISTQB: Static / Manual Testing
**Task:** Task 2
**Instructor:** Mina Younan

---

## 📌 Key Takeaways

This task provided practical experience in:

* Analyzing functional and non-functional requirements
* Designing manual test cases
* Executing functional test scenarios
* Performing exploratory testing
* Identifying and documenting defects
* Using browser developer tools
* Testing browser storage behavior
* Performing basic accessibility testing
* Performing basic performance testing
* Preparing structured test documentation
* Analyzing test execution results

---

## 🔗 Application

**Mina's Online Store:**
https://minayounan-cs.github.io/TestLab/products.html

---

### 👨‍💻 Author

**Mahmoud Bakri**
Software Testing Engineer Trainee | DEPI

GitHub:
https://github.com/MahmoudBakri225/

LinkedIn:
https://linkedin.com/in/mahmoud-bakri-swt/
