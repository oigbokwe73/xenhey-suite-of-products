Your [Xenhey Working-Capital Loans page](https://www.xenhey.com/api/store/DE087115DE48478BAAD4BA8F2C4A5909) opens a **Customer Dashboard** focused on applications. Its strongest next step is to connect **use of funds, loan offers, disbursement and scheduled repayment** into a complete customer experience.

I reviewed its HTML and JavaScript. I did not submit applications or test separately linked pages, record feeds or lender integrations.

**Working-Capital Loan UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/vQ3TXzdJdwQD_ANXgJtoXRJnxRS14QFC90izt5LUwV8c4VhONSNSc4lIINkCgCFWiaDbrmHCDVZ2yvljCAkq3iHhb-6jpgv90D5L15-Js7IUyTIyeHTAfJv5jVpmx1qiCrU5i1cEIs9wDu7O_34x_tRpjuQHx6Aazupu6pPXsDfdvPVdx5_URQABH-qIBQk-?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/0iMEBNKke33c3CLUOVGXQXItAOmP3llm5hJQgm0yf7x8g8nn_dJKdS8QeIFUE5LnDxaqfPgu_O4RLKMDkNw6Qpfe4YjoMzBAh1mAHphKZWKmiGsSn3gdfFiKY9C63OpZj795Re-MMc6GAVdcKGpSgbZlgK3DFxiQj7ZWqb-Nar4A2tWS3xsQ-XoLwQ6-IJi4?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/1Q4o96L6sfq3M4mtGvuVW_mwN9SYl1lzCtSEogJP9iFqoHVdP8FsPNdByf0kV6bplpAUem5COq06MXpXrcdz0i6s470srxxpa8OquDR8YirHwtS1zeSKb6EYr1ELS9gHu8uGMwngjIcT2WHP2NXQIvKWMpIWoGcXIUwcZ8yg2w5bhPPI9GwdbXtgoiyChnqw?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/bGNKJ0vEA3aVxKlLyAS--mgw9pb7bjPtzV2STcqsDbolO_xNNOwfQRkgxyVPox4s7hV0dIS2Y8EVOtOIdkeiSZ7bi15krzG98vBy9slurATU0ZgyZoRuB1KJLWCxcpp0ir7aCRbSzKNezTO1Yd3GkUDb7qZs2KTYxG0aIkJs89iqGJfG0nYyWH99tsskhPUC?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/YwBK4uRAhFdMN_EQJ9nVs-5E7xQvLhZY74akxpa8nF-mNdR7ZdCb0KdBnJFI49NFQrNUAwqU94r-ukXMmjaGGwspZt_U1mDfpgwFNW3Bx0ArWfUD0eveBJUJ3q0i0D3DVGTTz-4b4JfI3PuS0luyvNQBuhdDrISvgUMKPzMl5oUzQxMDWUiKJL61Flw0mLxK?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/GprdnAx_5WvjnOZON8zore36E1yaDVzHA5eDAcAh1kmdren4rWJLAArHJ1OgjQmI7pR8kBmYSnuBZ73ce-1zofLjktII7M6NhndxE3DnfBIar4UTYPX3T6cYn3SxQZ_G5EeE4_VXCzmY1f9iv4JL1JpQ9s6Fn2qi1vnbkK9hpo5E9fnteetLhO5NyCTPRj7Z?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/WRFESLpyjBOv14Dj-_8kW0RmDN6N2BMzs7nQ6U0m9BZ2Q03ygH7v45Rj54IMWFfZ7CZU-CAPWhGHAzD0Bwq-zojVpFvm9rwntC8fCwX0dCxYyDhwhQ5ItquWhkox8Q-uE4Tcnx-b3xvLP3pCPL9MPjuPIVQ0mIqTJZk-_FtPM0_R9ndssgZjBlQYEJeV4ge1?purpose=fullsize)

| Screen                | What users should see                                             | Primary actions                         |
| --------------------- | ----------------------------------------------------------------- | --------------------------------------- |
| Application dashboard | Requested amount, purpose, stage and outstanding requirements     | Continue application, provide documents |
| Use-of-funds planner  | Requested funding allocated across business needs                 | Add expense, adjust allocation          |
| Application wizard    | Business, financials, repayment source and supporting evidence    | Save, continue, review                  |
| Offer comparison      | Approved amount, net proceeds, term, payments, pricing and fees   | Compare, view terms, select             |
| Closing checklist     | Conditions, documents, signatures and funding readiness           | Resolve condition, sign                 |
| Funding status        | Confirmed proceeds, destination, processing status and reference  | Track disbursement                      |
| Active-loan dashboard | Outstanding principal, next payment, maturity and payment history | Make payment, view statement            |
| Payoff request        | Requested payoff date, quote status and valid-through date        | Request quote, view instructions        |

**Evaluation of your current implementation**

The page already includes an eight-step intake, field-specific dropdowns, searchable tables, CSV export and controls that load a selected sample application into the intake. Its product copy describes an amortizing loan with scheduled repayment. [Source: Xenhey Working-Capital Loans](https://www.xenhey.com/api/store/DE087115DE48478BAAD4BA8F2C4A5909).

| Finding                                                              | Recommended improvement                                                        |
| -------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| Dashboard stage, document count and next-review date are hard-coded  | Derive them from the selected application                                      |
| Requested amount and application-status details use the first record | Bind the interface to the selected customer and application                    |
| Customer table includes business records and risk tiers              | Enforce customer-scoped access; retain internal risk assessments in operations |
| Dashboard table has no direct View/Edit action                       | Add record-specific application links                                          |
| Wizard navigation redraws fields without preserving current input    | Save a working draft before changing steps                                     |
| Revisiting steps reloads the original selected record                | Restore the latest draft, including unsaved edits                              |
| Save Draft captures only the active section                          | Persist all eight sections under a stable application ID                       |
| Form submissions overwrite a shared form key                         | Merge sections and update the corresponding application record                 |
| Final submission validates only the displayed form                   | Validate the complete application and confirm backend submission               |
| Offers, payments and other screens reuse the application table       | Build dedicated offer, disbursement, payment and statement views               |
| Table uses `termMonths`, while intake uses `requestedTermMonths`     | Map requested and approved terms explicitly so edited values stay consistent   |

**1. Application dashboard**

Show one clear next action, supported by:

* Requested amount and requested term
* Financing purpose
* Current review stage
* Outstanding documents and conditions
* Desired funding date
* Assigned representative
* Last saved or updated time

Keep **requested**, **approved**, and **disbursed** amounts distinct. After funding, switch the primary dashboard to repayment and servicing.

**2. Use-of-funds planner**

Your intake currently captures the purpose in a selection and a text field. Add an editable allocation table.

*Illustrative allocation:*

| Use                  |       Amount | Needed by  | Supporting information |
| -------------------- | -----------: | ---------- | ---------------------- |
| Inventory purchase   |      $45,000 | October 1  | Supplier quote         |
| Payroll and staffing |      $30,000 | October 15 | Staffing plan          |
| Supplier payments    |      $15,000 | October 5  | Payables summary       |
| Marketing launch     |      $10,000 | October 20 | Campaign budget        |
| **Total requested**  | **$100,000** |            |                        |

Show any difference between the allocation total and requested loan amount. Allow users to explain timing and anticipated repayment sources.

**3. Loan application**

Retain your existing eight sections:

1. Business profile
2. Loan request
3. Operations and repayment
4. Financial profile
5. Collateral and guarantees
6. Ownership and control
7. Documents and review
8. Consent and submission

Add a persistent summary panel showing amount, term, purpose and completion status. The final page should display actual entered values with **Edit section** links.

When editing an application, preserve its ID, save all sections, update its timestamp and refresh the same table row. Parse checkboxes explicitly so a saved string `"false"` does not become checked.

**4. Offer-comparison UI**

Replace the generic offer-selection form with provider-issued offer cards.

| Comparison property       | Display                                          |
| ------------------------- | ------------------------------------------------ |
| Approved loan amount      | Confirmed offer amount                           |
| Net proceeds              | Amount after disclosed upfront deductions        |
| Term and frequency        | Number of months and payment frequency           |
| Scheduled payment         | Amount and whether it may change                 |
| Pricing                   | Rate type, applicable rate disclosures and fees  |
| Total scheduled repayment | Where determinable from the offered terms        |
| Security requirements     | Collateral and guarantees, where applicable      |
| Early repayment           | Applicable payoff and prepayment terms           |
| Conditions and expiration | Outstanding requirements and offer-validity date |

Use lender-supplied values. Any interactive payment estimate should be clearly labeled as an estimate with its assumptions.

**5. Closing and disbursement**

Provide a checklist with document status, owner, due date and action. Then show funding separately:

| Status                   | Customer-facing meaning                            |
| ------------------------ | -------------------------------------------------- |
| Conditions under review  | Required items are being checked                   |
| Ready for funding review | Closing requirements are prepared for final review |
| Disbursement scheduled   | A transfer has been scheduled                      |
| Processing               | Funds are being transferred                        |
| Disbursed                | Provider confirmation is available                 |
| Exception                | An issue requires attention                        |

A signed agreement should not automatically mark the loan disbursed.

**6. Active-loan dashboard and payments**

After funding, prioritize:

* Original loan amount
* Outstanding principal
* Next payment amount and due date
* Scheduled-payment status
* Remaining term and maturity
* Recent payment activity
* Statements and support requests

The repayment table should distinguish **scheduled**, **processing**, **posted**, **failed**, and **reversed** payments. Show principal, interest and fees separately when supplied by the servicing system.

Outstanding principal should not be presented as an exact payoff amount. Use the existing payoff-request flow to obtain a dated, provider-confirmed quote.

**Recommended implementation order**

1. Fix complete-application saving and record-specific editing.
2. Scope dashboard data to the selected business.
3. Add the use-of-funds planner and final application review.
4. Build offer comparison and closing-condition screens.
5. Add confirmed disbursement, repayment history and payoff tracking.
