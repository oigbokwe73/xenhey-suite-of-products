Your [Xenhey POS Financing / BNPL page](https://www.xenhey.com/api/store/0CE14C5BF21740F0A5557967A3946B39) is a product landing page with bundled checkout, application, repayment and operations screens. The main opportunity is to make **plan selection and repayment schedules** central to the customer experience.

I reviewed its HTML and JavaScript. I did not submit applications or test the connected pages.

**BNPL UI inspiration**

These images are design references, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/e9IJPHDCyOxnxLPOJeAHv7jxInyHnAtTlbnW4N0ndOew40f-MudbqwdiBptSFWxSuKLtQnr-LRx1WTdGOa37pC9VrU-mCApjkXGrf8tfJkXWmmdIh3HfEZZf7U0DVxZJ-n-YuB3djlu7pWmULKRzkhNXmTC9dtgenwYXmIQ9dIeb6rrbCuCfdCJCuZ-UOK4v?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/xjiIlyunuNZidPhWkENTm_4G4J8ge6VAy2uzwQD1tw6sAjarpl2anzslmhEbjJ2QUWycAKHOKoCUyCaggPJY6OQK4hZo2phGk7UQJ-CTE-mMMUXUDUIZda798sNz-qfjB7OukxVenL-pSXyAStKTxeLpkNBZkNQeOJZVsNi3qA1d4R8RtwpvV8l-LJW4okma?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Eyw9YLGsPVbTZRfURG2wpLjFubRHPIvAY17mH6UMBnCxPgFKzTSBrPfIS6SUsej16D-UTQiUPpyn1h6Y2NDW6VcGxgg3f-vHKV8zN4gdfsEXNbrRFstgqAXTp0j4FdSLryBrKNLcP5FrnjseI_qQZfPUz0yekfUTYCXnpKw2LpBmZqnwAEbKJl-WZZLkly0C?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/xd_YivLdUerj30p5DI7Tguzpw5IEHiQ8mmK0ML4rteNld8vbmdfhHaG2TnCPvx9N8ju81VcJRoOl_MwDIsJvKIAzwYNeznxYMNLWpzLvPTycFBift4YCFHbBVtEkeSVFUvpwSUYmd8mYGstBtKkUSKX3N507fjgBTFNOvad6USkhNKClwHC50vVduU1LxeBa?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/lhy49C-0CLjj1Oq_VCyPn0nlhdhbH1GNo_V8cuBdVgsrmgEunkiKGLVsCqEyP5ODgObWdwd1f8o4_fGZ1RB-LJe7pXrSAdFjtn2h_rHwlrAyaIqDkPmi44HET8OW3nvALt-VZ3RlHgbW_-6E4QssVko4xeWBu19cFzxqiawAX6200pBi9oSgVadpUGT94mVq?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Kiwh3bsC82kQ10Zs5y70dfn7ORh7mvichKteGCvHNgxAMveL2FBynw3i9TWIXa9yZ9YwQ_yU5J5BekDxTH-_FQJB7tQGn8GrpQfDn7tXC0jg0yRpKJbJ-Rw0Znie57Scl-y4iEQ16sVWHpBOTOgvobiDRbTS76ZmbiiJLthsu8usZFBceMHQKzXJRUh7v4tS?purpose=fullsize)

| UI example          | What it should display                                                    | Main actions                  |
| ------------------- | ------------------------------------------------------------------------- | ----------------------------- |
| Checkout financing  | Merchant, order summary, purchase amount and financing options            | Explore plans, continue       |
| Plan comparison     | Amount due today, installment amounts, dates, APR, fees and total payable | Select plan, view terms       |
| Application         | Required applicant information, verification and progress                 | Save, continue, review        |
| Offer acceptance    | Exact offered terms, complete schedule and disclosures                    | Accept, decline               |
| My plans            | Merchant, remaining balance, next payment and plan status                 | View plan, manage payment     |
| Repayment details   | Paid, upcoming, processing and overdue installments                       | Pay, view receipt, get help   |
| Returns and refunds | Order return status, refund amount and resulting plan adjustment          | Report return, track refund   |
| Merchant operations | Orders, authorizations, settlements and refunds                           | View order, reconcile, refund |

**Evaluation of your current page**

Your source includes useful coverage: a nine-step application, payment-method references, identity and affordability review, disclosures, orders, refunds, disputes, settlements and collections. However, several screens are still generic placeholders. [Source: Xenhey BNPL page](https://www.xenhey.com/api/store/0CE14C5BF21740F0A5557967A3946B39).

| Finding                                                                                                   | Recommendation                                                                           |
| --------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Landing page presents installments, merchant integration and returns as three equal cards                 | Lead with the shopper’s purchase and plan choices; give merchants a separate entry point |
| Checkout is a generic form                                                                                | Build an order summary plus financing-selection experience                               |
| Installment Plans falls back to generic status/notes fields                                               | Create a dedicated plan-detail screen with the full repayment schedule                   |
| Customer dashboard labels a column “Next payment,” but the sample values are risk labels such as “Medium” | Replace reused application rows with plan-specific records                               |
| Dashboard totals and progress stages are fixed sample values                                              | Calculate totals and stages from the selected customer’s records                         |
| Wizard navigation redraws fields without preserving current input                                         | Save and restore each step before navigation                                             |
| Main Save Draft stores only the current step                                                              | Persist the complete application under a stable ID                                       |
| Step saves overwrite the same form-storage key                                                            | Merge all sections into one application record                                           |
| Final submission only logs a fixed sample ID and shows a toast                                            | Validate the full application and wait for confirmed persistence                         |
| Customer application exposes device-risk and fraud-review fields                                          | Show verification progress to customers; keep risk assessments in operations             |

**1. Checkout and plan-selection UI**

Use a two-column desktop layout: order summary on the left, plan options on the right. Stack these vertically on mobile.

The order summary should show merchant, items, taxes, shipping, purchase total and order reference. Each offered plan should display:

* Amount due today
* Number and frequency of installments
* Exact payment amounts and dates
* APR, applicable fees and total payable
* Offer expiration, where applicable
* Link to the plan’s terms

Render these values from provider-returned offers. Do not imply that every purchase qualifies for the same installment structure.

**2. Repayment schedule UI**

Example only: a synthetic $840 purchase split into four $210 payments, with no interest or fees in this illustration.

| Installment | Due date           |  Amount | Status    |
| ----------- | ------------------ | ------: | --------- |
| 1           | September 12, 2026 | $210.00 | Paid      |
| 2           | September 26, 2026 | $210.00 | Upcoming  |
| 3           | October 10, 2026   | $210.00 | Scheduled |
| 4           | October 24, 2026   | $210.00 | Scheduled |

Above the schedule, show **$630 remaining**, the next due date, masked payment method and autopay status.

Provide **View payment details**, **Manage payment method**, and **Get help**. Offer early-payment or rescheduling controls only when the provider supports them.

**3. Customer dashboard UI**

Replace the shared application table with a dedicated “My plans” table.

| Plan      | Merchant              | Remaining | Next payment | Due date | Status    |
| --------- | --------------------- | --------: | -----------: | -------- | --------- |
| PLAN-1001 | Harbor Home Goods     |      $630 |         $210 | Sep 26   | Active    |
| PLAN-1002 | Metro Electronics     |      $400 |         $100 | Sep 28   | Active    |
| PLAN-1003 | Northstar Furnishings |        $0 |            — | —        | Completed |

*Illustrative records.*

Use separate sections for:

* Applications awaiting a decision
* Active repayment plans
* Upcoming payments
* Returns and disputes
* Completed plans

Keep internal risk ratings out of the customer table.

**4. Returns and refund UI**

A return and a financing adjustment should have distinct statuses.

| Stage             | Customer-facing information                     |
| ----------------- | ----------------------------------------------- |
| Return reported   | Merchant, items, requested refund and reference |
| Merchant review   | Whether the return has been accepted            |
| Refund processing | Confirmed refund amount and processing status   |
| Plan adjusted     | Revised remaining balance and payment schedule  |

Show the provider-confirmed payment obligations while a return is pending. Do not assume a return automatically pauses installments.

**5. Merchant and operations UI**

Give merchant users a focused order-and-money workspace:

* Order and authorization status
* Captured amount
* Refunds
* Settlement batch
* Gross amount, fees and net settlement
* Exceptions requiring action

Reserve identity review, affordability assessment, fraud decisions and collections for authorized financing-operations staff.

**Recommended implementation order**

1. Fix application saving, restoration and final submission.
2. Create distinct application, order, offer, plan, installment and refund records.
3. Build plan comparison and acceptance with provider-configured terms.
4. Replace generic tables with accurate repayment and transaction views.
5. Add refund adjustments and merchant reconciliation.

This gives your Xenhey flow a clear progression: **purchase → financing offer → acceptance → repayment → completion**, with returns and disputes connected to the relevant order and plan.
