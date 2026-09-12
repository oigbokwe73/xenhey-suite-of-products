Your [Xenhey Bookkeeping Subscriptions page](https://www.xenhey.com/api/store/1163B715C77D4D9084125C6788A0F919) opens a **Business Dashboard** focused on transaction review, reconciliation and monthly close. It provides a useful workflow foundation, but needs dedicated bookkeeping screens and subscription-management features to become a complete customer experience.

I reviewed the page’s HTML and JavaScript. I did not submit forms or test the separately linked pages.

**Bookkeeping UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/CCmU8ERcdjmfCRPzR9lEetRasFSI_EsNpDJc4qxmmoP51dNlMAebhrmhJFNOeRMG9F-uhJeOucfd9iDGcXCeHtUgnEpsd8VJH2zvlCgOnnKsmtKsep8bSpNeALUZJORcXGORTj010L_eqDSdFTCjWhwG5NtlnOtJ9dYqAzRxU7eBx51EiNL_ANYAlI-RXZjc?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/d4AHjK-xMDgsXF7MCIE-USA7pKkZY0GLpZ-Pt9djM1oyz84N1Cg-Z0eQ-WA_cjsqgwT3d2G3eJn4qYJ7AM9UQ4ymjAVzhtXnaQMz244U0VHBUc5vEw6WQvJY-sQJLV2BjUVppxoa3AqM3T9ZT2yEbxGvQmknXxz4ZKJrhOlPokaWOSSOlyjZ8EIWBvy-cfP-?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/3h-gfTzsyLcTB_4KHRSYCYkXDOIQ9vgaTsiXf8x-FUFVayaxOngiPXi9ToZEQI4RMDk2TtYve2DIY0qGm4IojVzd3rjvXKgnpQtSj90MKK4kbcxQiP2CpauX_Wh_ODXSPUKtH0lp7eGVTe6OZZE4_4thQ3Xwc9J1MYAoMPZhRcOpic0whiShWQyLa_mbZ3lY?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/QqUjNZ0RvykXSiPetXP1buFLYpIR8wxPqYF1ziW39n9q5NWj3NhATJJh-Nd-9ogTZRaDZ4ZSmkH76zjQRIrouy2tijG9gNJJdco0qtvwKsMtbQ_437ume-1XbSWOdiSxOlf3xVV6h6D05wcEkRyBzdEyEWiVGtOgbiNN3auqmd4rPOyk3SI3vbS8LHwHqXI6?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Pqg7n8U0rRKLpJXm88zadT6ZeNR8sqCu_KI4b2CJ9o-SCYSAYD506trXfxNyPhaiA-tyQ-dLaMrgxNgE2cSdtwZEI7TBZaS6pojvTqnB1E-GI_zWsxKpZxLGEzMMT2iHyP8WDQcT79WABl2_iLOyaec4FbSH4v_Q5-7BzPtO129gHlgUFKJzdz8CZLGY7KeK?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/smOY7FD1pp_XiwYEL9ZtQbMvHTbZuDj3TRegINPbJYrMMRfln6ysA0w4j7bGdVUV79nLFPJKUU_fHuDGMwogCVnHzOUF52XtQPEPxBC7uuBwGsp56_8aPU5VdNbfzqFmR98bx3-fGlrKmNwSvTn9lN7IY2KNHyQeNk972AGtPgq90wTaa-Ye3m8OdpbVN1X2?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/IyJe2qelNwSlhJBc8eLQNIU6S76vDAcu4Ao4qGIq8E6g_uBl66yO8k9fbpOkpKITtutcwZ9wIMdJln1uHWhw7kYEb2qgn-AA6IfQZEXojo4g02Vp5G2b_XzUpyXrczGp2TNzR15ph7RnPaFRnm85udEQ3RNG9YDVGUlnN-2kNE38f9qPMYUR5hm6hdUotKdG?purpose=fullsize)

| UI example              | What users should see                                                                  | Primary actions                    |
| ----------------------- | -------------------------------------------------------------------------------------- | ---------------------------------- |
| Business dashboard      | Current reporting period, close progress, outstanding requests and assigned bookkeeper | Review requests, view reports      |
| Subscription management | Selected plan, included services, usage, renewal date and invoices                     | Compare plans, manage subscription |
| Onboarding              | Company, accounting system, opening balances and connection readiness                  | Continue setup, save draft         |
| Transaction review      | Transactions, proposed categories, receipts and review status                          | Categorize, split, attach receipt  |
| Reconciliation          | Statement and book balances, matched items and unresolved differences                  | Match, investigate, complete       |
| Monthly close           | Tasks, owners, dependencies, deadlines and reviewer approval                           | Resolve blockers, review close     |
| Financial reports       | Income statement, balance sheet and available supporting schedules                     | View, compare, download            |
| Document requests       | Requested evidence, related transaction, deadline and status                           | Upload, comment, respond           |
| Bookkeeper workspace    | Client queues, exceptions, due dates and workload                                      | Assign, review, follow up          |

**Evaluation of your current page**

The embedded implementation covers company setup, chart of accounts, transactions, receivables, payables, reconciliation, reporting and quality review. Its product page defines **Essential Books**, **Books + Close**, and **Full-Service Finance Ops**. [Source: Xenhey Bookkeeping Subscriptions](https://www.xenhey.com/api/store/1163B715C77D4D9084125C6788A0F919).

| Finding                                                                                                                              | Recommended improvement                                                                       |
| ------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------- |
| Dashboard shows fixed values: 72% close progress, 12 uncategorized transactions, six of eight accounts reconciled and three requests | Calculate these for the selected company and reporting period                                 |
| The same setup-progress tracker appears in ongoing bookkeeping views                                                                 | Separate onboarding progress from recurring monthly-close progress                            |
| Transactions, reconciliation and receivables reuse generic client sample rows                                                        | Create dedicated records, columns and actions for each screen                                 |
| Financial Reports displays a configuration form and generic table                                                                    | Render actual report previews, period comparisons and download links                          |
| Generic dropdowns reuse “Yes,” “Pending,” “Connected,” etc.                                                                          | Define appropriate choices for accounting basis, account type, service plan and review status |
| Wizard navigation redraws fields without preserving current input                                                                    | Save section values before navigation and restore them when revisited                         |
| Main Save Draft stores only step and timestamp                                                                                       | Persist the complete intake under a stable client/intake ID                                   |
| Each step saves to the same form key                                                                                                 | Merge sections instead of overwriting prior answers                                           |
| Final submission logs a fixed reference and shows a toast                                                                            | Validate the complete intake and confirm persistence                                          |
| Client links omit the selected client ID                                                                                             | Open the correct client using a stable identifier                                             |
| Navigation lacks a dedicated subscription/billing workspace                                                                          | Add plan details, service scope, usage, billing history and change requests                   |

**1. Business dashboard**

Make **“What needs my attention?”** the main focus.

Recommended modules:

* **Books through:** latest completed period
* **Current close:** progress, target date and blockers
* **Your action items:** missing receipts and transaction questions
* **Account connections:** last successful sync and reconnect requests
* **Latest reports:** publication date and reporting period
* **Your bookkeeper:** assigned contact and messages
* **Your subscription:** current plan and included services

Label financial figures as draft or finalized, and show their accounting basis and reporting period.

**2. Subscription-management UI**

Your service tiers should have an explicit comparison screen.

| Property              | UI treatment                                        |
| --------------------- | --------------------------------------------------- |
| Monthly price         | Configured price and billing frequency              |
| Included services     | Categorization, reconciliation, close and reporting |
| Transaction allowance | Included volume and how usage is counted            |
| Connected accounts    | Included account allowance, if applicable           |
| Historical cleanup    | Included, separately quoted or unavailable          |
| Delivery schedule     | Agreed close and report-delivery targets            |
| Support               | Assigned contact, channels and service hours        |
| Additional work       | Clearly identified charges or approval requests     |

Include **View agreement**, **Download invoice**, **Request plan change**, and **Manage subscription**. Display confirmed service terms rather than invented package limits.

**3. Transaction-review UI**

Use a table with a details panel for the selected transaction.

*Illustrative records:*

| Date   | Description         |     Amount | Proposed category   | Receipt      | Status                   |
| ------ | ------------------- | ---------: | ------------------- | ------------ | ------------------------ |
| Sep 8  | Office supply store |   −$245.80 | Office supplies     | Attached     | Ready for review         |
| Sep 9  | Customer payment    | +$4,200.00 | Needs matching      | Not required | Match invoice            |
| Sep 10 | Online marketplace  |   −$186.45 | Needs clarification | Missing      | Customer response needed |

Recommended actions:

* Confirm or change category
* Split a transaction
* Match an invoice, bill or transfer
* Attach supporting evidence
* Ask the customer a question
* Review change history

Keep suggested categorization distinct from approved or posted entries.

**4. Reconciliation UI**

Use a statement summary above two matching panels: **statement items** and **book entries**.

| Summary field            | Purpose                                           |
| ------------------------ | ------------------------------------------------- |
| Account and period       | Establish which statement is being reconciled     |
| Statement ending balance | Source statement value                            |
| Adjusted book balance    | Balance after relevant reconciliation adjustments |
| Unresolved difference    | Amount still requiring investigation              |
| Outstanding items        | Unmatched transactions and their age              |
| Review status            | In progress, prepared, reviewed or completed      |

The current `differenceAmount` field should be calculated from the reconciliation model, not manually entered as the final result. Completion should also require review of outstanding items and supporting evidence.

**5. Monthly-close workspace**

Replace the static progress strip with a task checklist.

| Task                | Owner      | Status                | Blocker                   |
| ------------------- | ---------- | --------------------- | ------------------------- |
| Review transactions | Bookkeeper | In progress           | Three customer questions  |
| Reconcile accounts  | Bookkeeper | Six of eight complete | Two statements missing    |
| Review receivables  | Bookkeeper | Ready for review      | —                         |
| Review payables     | Bookkeeper | Complete              | —                         |
| Review adjustments  | Reviewer   | Pending               | Reconciliation incomplete |
| Publish reports     | Reviewer   | Not started           | Close approval required   |

Add due dates, comments, supporting references and a controlled reopen action for completed periods.

**6. Reports and customer requests**

The report screen should offer an income statement, balance sheet, trial balance, general ledger and relevant aging reports. Show the period, accounting basis, preparation status and last update.

For requests, provide a focused customer inbox:

| Request                   | Related item               | Due    | Action  |
| ------------------------- | -------------------------- | ------ | ------- |
| Provide purchase receipt  | Transaction TX-1042        | Sep 15 | Upload  |
| Explain incoming deposit  | Transaction TX-1049        | Sep 15 | Respond |
| Provide monthly statement | Operating account ••••4821 | Sep 16 | Upload  |

Use secure document handling and synthetic data for the browser-storage prototype.

For Xenhey, prioritize **complete intake persistence → dedicated transaction and reconciliation screens → monthly-close tasks → report previews → subscription management**. This makes the service’s ongoing value and the customer’s next action visible.
