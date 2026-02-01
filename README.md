# TestCase_Gen_Prompt_AddToCart_Feat

Role:
QA Lead — 15+ years automation experience (Selenium, Java, Maven, Salesforce domain). Responsible for producing a complete, enterprise-grade test cases to validate the Add to Cart feature.

Instructions:
Create test cases for Add to cart feature for "https://www.bstackdemo.com/". The testcases must be precise, actionable, and include acceptance criteria, test data, edge cases, and required artifacts.

Context:
Feature: Add to Cart
Given business rules: Users can add products to cart; maximum 10 items per product; cart shows total price.
Non-functional constraints: Real-time cart update; client-side and server-side validation for quantity limits; accurate price calculation including unit price, quantity, discounts, taxes (if applicable).

Examples:

Positive scenarios (sample)

• AddSingleItem — Add 1 unit of Product A; cart shows quantity 1 and total = unitPrice  1.
• AddMaxAllowed — Add 10 units of Product B; cart accepts and total = unitPrice  10.
• AddMultipleProducts — Add Product A (2 units) and Product B (3 units); cart shows both line items and total = sum of line totals.
• IncrementFromCart — Add 1 unit, then increase quantity to 3 from cart UI; total updates accordingly.

Negative scenarios (sample)

• ExceedMaxLimit — Attempt to add 11 units of Product C; system blocks action and shows error: "Maximum 10 items allowed per product."
• RapidClicks — Click Add to Cart repeatedly (race condition); cart should not exceed 10 units and should remain consistent.
Boundary tests
• LowerBoundary — Add exactly 1 unit.
• UpperBoundary — Add exactly 10 units.
Integration checks
• PricePrecision — Unit price with decimals (e.g., 19.99) multiplies correctly and total rounds to two decimals.
• Test user account exists (or guest flow enabled).
• Product catalog contains test products with known unit prices and stock >= 

Edge-case handling
• If product stock < requested qty, expect stock-limit message.
• If network latency causes delayed cart update, include retry logic and timeouts in automation.
Test prioritization and severity
• P0 (Critical): AddSingleItem, ExceedMaxLimit, PricePrecision, AddMultipleProducts.
• P1 (High): IncrementFromCart, ZeroOrNegativeQuantity, RapidClicks.
• P2 (Medium): Integration with discounts/taxes, guest vs authenticated differences.

Output: Generate a Word document for this