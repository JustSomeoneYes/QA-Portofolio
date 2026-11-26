# Test Plan: SauceDemo E-Commerce Application

**Author:** Stana Bogdan
**Date:** November 2026  
**Application Under Test (AUT):** [SauceDemo](https://saucedemo.com) (v1)

---

## 1. Objective

The purpose of this test plan is to define the testing scope, approach, resources, and schedule for verifying the core e-commerce workflows of the SauceDemo web application. Testing will focus on functional accuracy, input validation, and UI consistency across critical user journeys.

---

## 2. Scope

### In-Scope Features

- **Authentication:** Valid login (`standard_user`), restricted access (`locked_out_user`), and invalid credential error handling.
- **Product Inventory:** Product listing display, image rendering, price accuracy, and sorting functionality (Name A–Z, Name Z–A, Price Low–High, Price High–Low).
- **Shopping Cart:** Adding/removing items from both the inventory and product detail pages, cart badge counter updates, and cart state persistence during navigation.
- **Checkout Flow:** Customer information form validation (First Name, Last Name, Zip/Postal Code), item subtotal calculation, tax calculation (8%), final total accuracy, and order confirmation.
- **Session Management:** User logout and cart reset functionality via the side navigation menu.

### Out-of-Scope Features

- **Payment Gateway Integration:** SauceDemo uses a mock checkout completion flow; real credit card processing and third-party payment APIs are excluded.
- **Backend & Database Verification:** Direct SQL/API testing is excluded due to lack of backend access on the demo environment.
- **Performance & Load Testing:** Stress testing high concurrent user traffic is outside the scope of this functional test cycle.
- **Mobile Native Apps:** Testing is restricted to mobile-responsive browser viewports rather than native iOS/Android builds.

---

## 3. Test Approach & Types

- **Smoke Testing:** Verify core navigation, login, and checkout paths work before deeper testing.
- **Functional Testing:** Execute positive, negative, and boundary test cases against all in-scope features.
- **Exploratory Testing:** Use built-in test personas (`problem_user`, `visual_user`) to uncover hidden UI, state, and functional defects.
- **Automated Regression:** Automate critical end-to-end happy paths and key negative validations using Playwright.

---

## 4. Test Environment

- **Operating System:** Windows 11 Pro
- **Browsers:** Opera GX (Latest)
- **Resolution:** Desktop (`1920x1080`) and Mobile Viewport (`375x812` via DevTools)
- **Tools:** GitHub (Documentation), Playwright (Automation), OBS / Snipping Tool (Bug Evidence)

---

## 5. Entry & Exit Criteria

### Entry Criteria

- Application URL (`https://saucedemo.com`) is accessible and responsive.
- Test user credentials provided on the login page are active.
- Test cases are documented and reviewed prior to execution.

### Exit Criteria

- 100% of planned manual test cases (15–20 cases) have been executed.
- All discovered functional and UI defects are documented with reproducible steps and visual evidence.
- Automated Playwright smoke suite (5+ tests) executes cleanly without script errors.

---

## 6. Risks & Mitigation

- **Shared Demo Environment:** Because SauceDemo is a public sandbox, state or performance may occasionally fluctuate. _Mitigation:_ Use the "Reset App State" menu option before starting new test runs.
- **Intentional Defect Personas:** Certain test accounts (`problem_user`) are designed to fail. _Mitigation:_ Document defects objectively as if discovered in a staging environment before release.
