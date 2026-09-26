The Xenhey prototype confirms a **Business Customer** experience centered on a Business Credit Cards dashboard/card account and a separate **Card Operations / Admin Dashboard**, with navigation between Customer Flow, Admin Flow, and the broader Financial Product Catalog. Xenhey also explicitly identifies the experience as a prototype using representative sample data rather than guaranteed approvals, rates, limits, pricing, or rewards. :chatgpt-content-reference{index="0"}

The 64 sections below expand that prototype into a comprehensive **Business Credit Cards functional specification**. The detailed workflows, rules, and fields are an architectural/product expansion of the Xenhey prototype rather than a claim that every field below is already implemented on the public page.

---

# Business Credit Cards — Detailed 64-Feature Specification

## 1. Business Credit Card Customer Dashboard

The Customer Dashboard should act as the central landing page after authentication. It should give the business owner, finance administrator, or authorized account manager an immediate view of the organization's credit-card relationship.

The dashboard should display:

- Business account name.
- Masked account number.
- Overall account status.
- Total credit limit.
- Current balance.
- Statement balance.
- Available credit.
- Pending authorizations.
- Minimum payment due.
- Payment due date.
- Credit utilization percentage.
- Total number of active cards.
- Locked or suspended cards.
- Employee cards.
- Recent transactions.
- Rewards balance.
- Open disputes.
- Fraud alerts.
- Recent notifications.

### Quick actions

The dashboard should allow users to immediately:

- Make a payment.
- Add an employee card.
- Lock a card.
- Unlock a card.
- Report fraud.
- Replace a card.
- View transactions.
- Download statements.
- Manage spending limits.
- View rewards.
- Update account information.

### Dashboard personalization

Different roles should receive different dashboard views. A business owner might see enterprise-wide balances while an employee cardholder may only see transactions associated with their individual card.

This Customer-versus-Admin separation aligns with the prototype's explicit Business Customer dashboard and Card Operations admin experience. :chatgpt-content-reference{index="1"}

---

# 2. Business Credit Card Product Catalog

The Product Catalog provides the acquisition experience before the customer chooses a card.

Each product should display:

- Product name.
- Card artwork.
- Product category.
- Annual fee.
- Purchase APR information.
- Promotional APR.
- Cash-advance APR.
- Foreign transaction fee.
- Late-payment fees.
- Rewards structure.
- Welcome bonus.
- Employee-card fee.
- Travel benefits.
- Purchase protection.
- Fraud protection.
- Expense-management capabilities.
- Recommended business profile.

### Product categories

Possible products could include:

- Basic Business Credit Card.
- Business Cashback Card.
- Business Rewards Card.
- Business Travel Card.
- Purchasing Card.
- Corporate Expense Card.
- Fleet/Fuel Card.
- Virtual Purchasing Card.

### Product discovery

Customers should be able to filter cards by:

- No annual fee.
- Cashback.
- Travel.
- Low APR.
- Large business.
- Small business.
- International use.
- Employee-card functionality.

The prototype includes navigation to a broader Financial Product Catalog, making this catalog integration a natural part of the solution architecture. :chatgpt-content-reference{index="2"}

---

# 3. Business Credit Card Application

The application module captures the information required to request a business credit-card account.

### Business information

Capture:

- Legal business name.
- DBA/trade name.
- EIN/TIN.
- Business structure.
- Industry.
- NAICS/SIC classification where required.
- Formation date.
- State of formation.
- Number of employees.
- Annual revenue.
- Expected card spending.
- Business phone.
- Business email.
- Website.
- Physical address.
- Mailing address.

### Applicant information

Capture:

- First name.
- Last name.
- Job title.
- Ownership percentage.
- Business role.
- Phone.
- Email.
- Residential address.
- Date of birth where legally appropriate.
- Identification information.
- Authorization authority.

### Application behavior

Support:

- Save draft.
- Resume application.
- Validate data.
- Upload documents.
- Review before submission.
- Electronic disclosures.
- E-signature.
- Submission confirmation.

---

# 4. Application Wizard

Rather than presenting all fields at once, the system should organize onboarding into an easy-to-follow wizard.

### Suggested sequence

**Step 1 — Product Selection**

Choose a card product.

**Step 2 — Business Information**

Enter organization information.

**Step 3 — Ownership**

Identify owners and controlling persons.

**Step 4 — Authorized Representative**

Identify the individual submitting the application.

**Step 5 — Financial Information**

Provide revenues, expenses, expected spend, and requested limit.

**Step 6 — Cardholder Setup**

Optionally create employee cards.

**Step 7 — Documents**

Upload requested supporting documents.

**Step 8 — Disclosures**

Review legal terms.

**Step 9 — Review**

Confirm information.

**Step 10 — Submit**

Send application.

### UX requirements

Include:

- Progress bar.
- Completion percentage.
- Back/Next buttons.
- Autosave.
- Error indicators.
- Inline validation.
- Tooltips.
- Help text.
- Save-and-return functionality.

---

# 5. Business Financial Information

Financial data allows the issuer to understand the business's ability to manage the requested credit line.

Capture information such as:

- Annual revenue.
- Gross receipts.
- Monthly revenue.
- Net income.
- Operating expenses.
- Existing business debt.
- Current commercial loans.
- Existing card debt.
- Cash balances.
- Expected monthly card spend.
- Requested credit limit.
- Existing relationship with the financial institution.
- Years in business.

### Derived information

The system may calculate:

- Debt-to-revenue ratio.
- Requested credit versus revenue.
- Expected utilization.
- Existing exposure.
- Total institutional exposure.

### Validation

Values should support:

- Currency formatting.
- Minimum/maximum validation.
- Reasonableness checks.
- Required-field rules.
- Cross-field consistency.

---

# 6. Beneficial Ownership / KYC

This capability identifies the people who own or control the business.

### Information captured

For each beneficial owner:

- Full legal name.
- Ownership percentage.
- Address.
- Date of birth where applicable.
- Identification details.
- Country of citizenship/residence.
- Relationship to organization.

### Control person

Capture the individual primarily responsible for controlling the organization.

Examples:

- CEO.
- President.
- CFO.
- Managing member.
- General partner.

### Verification status

Each party could have statuses such as:

- Not started.
- Pending.
- Verified.
- Failed.
- Manual review.
- Additional information required.

### Administrative view

Operations personnel should see:

- Verification source.
- Timestamp.
- Match result.
- Failed attributes.
- Review comments.
- Escalation status.

---

# 7. Application Review

Before final submission, customers should receive a complete application summary.

Sections should include:

- Selected card product.
- Business information.
- Ownership.
- Authorized representative.
- Financial information.
- Requested limit.
- Employee cards.
- Supporting documents.
- Contact preferences.

Each section should provide an **Edit** action.

### Review controls

Show:

- Missing required fields.
- Validation warnings.
- Certification statements.
- Consent checkboxes.

The applicant should certify that information is complete and accurate before submission.

---

# 8. Terms, Agreements and Disclosures

The application must make relevant terms available before account opening.

Possible documents include:

- Cardholder agreement.
- Business card agreement.
- Rates and fees disclosure.
- Rewards agreement.
- Privacy notice.
- Electronic communications consent.
- Personal guarantee terms when applicable.
- Authorized-user terms.
- Data-sharing notice.

### Tracking

Store:

- Document version.
- Effective date.
- User accepting.
- Acceptance date/time.
- IP/session metadata as appropriate.
- Document identifier.

This provides evidence of the exact terms accepted by the applicant.

---

# 9. Application Submission

Submission should create an immutable application record.

### Confirmation page

Display:

- Application number.
- Business name.
- Product requested.
- Requested credit limit.
- Submission timestamp.
- Current status.
- Next step.
- Contact information.

### Backend actions

Submission could trigger:

1. Validation.
2. Business verification.
3. Identity verification.
4. Fraud checks.
5. Underwriting.
6. Rules-engine evaluation.
7. Manual-review routing where necessary.

The application should not disappear if one downstream service temporarily fails.

---

# 10. Application Status Tracking

The customer should have a self-service tracker.

Possible statuses:

- Draft.
- Submitted.
- Received.
- Verification underway.
- Under review.
- Additional documents required.
- Underwriting.
- Approved.
- Conditionally approved.
- Declined.
- Card production.
- Card shipped.
- Active.

### Timeline view

Display events such as:

**September 14** — Application submitted  
**September 14** — Business verification completed  
**September 15** — Underwriting review  
**September 15** — Approved  
**September 17** — Card shipped

Customers should receive notifications whenever important statuses change.

---

# 11. Business Card Account Management

After approval, the application converts into an active account relationship.

The Account page should expose:

- Account ID.
- Account status.
- Credit limit.
- Current balance.
- Available credit.
- Pending transactions.
- Statement balance.
- Payment due.
- Rewards balance.
- Cards.
- Authorized users.
- Account administrators.

### Account-level actions

Authorized users can:

- Make payments.
- Request limit changes.
- Update contact information.
- Configure alerts.
- Add users.
- Manage cards.
- View statements.
- Export transactions.

---

# 12. Employee / Authorized User Cards

A major differentiator between personal and business cards is employee-card management.

### Add employee

Capture:

- Name.
- Employee ID.
- Email.
- Phone.
- Department.
- Cost center.
- Manager.
- Job title.

### Card configuration

Configure:

- Card spending limit.
- Daily limit.
- Monthly limit.
- Transaction limit.
- Cash access.
- International spending.
- Online purchasing.
- Merchant-category restrictions.

### Employee-card lifecycle

Statuses may include:

- Requested.
- Approved.
- Produced.
- Shipped.
- Activated.
- Locked.
- Suspended.
- Closed.

---

# 13. Spending Controls

Business administrators should be able to configure granular card policies.

Controls can include:

### Monetary limits

- Per transaction.
- Daily.
- Weekly.
- Monthly.
- Quarterly.

### Merchant controls

Allow or block:

- Restaurants.
- Hotels.
- Fuel.
- Airlines.
- Entertainment.
- Office supplies.
- Software.
- Professional services.

### Channel controls

Enable/disable:

- Card-present transactions.
- Online purchases.
- Contactless.
- ATM.
- Cash advance.
- International transactions.

### Real-time behavior

A transaction violating policy can:

- Be declined.
- Trigger an alert.
- Require approval.
- Be flagged for review.

---

# 14. Card Management

A centralized card screen should show every card attached to an account.

Columns may include:

- Cardholder.
- Last four digits.
- Card type.
- Department.
- Status.
- Spending limit.
- Available amount.
- Expiration.
- Last transaction.

### Card actions

Authorized users can:

- View.
- Lock.
- Unlock.
- Replace.
- Close.
- Activate.
- Modify limits.
- Modify spending controls.

---

# 15. Activate Card

Card activation should be simple but secure.

### Workflow

1. User selects card.
2. System verifies identity/session.
3. User confirms card information.
4. Activation request is submitted.
5. Card processor updates status.
6. Confirmation appears.

### Activation state

Track:

- Activation pending.
- Activated.
- Failed.
- Already active.
- Card blocked.

Activation events should be auditable.

---

# 16. Lock / Unlock Card

Customers should be able to temporarily suspend a card.

### Lock reasons

Examples:

- Card temporarily misplaced.
- Suspicious activity.
- Employee leave.
- Expense-policy issue.
- Administrative hold.

### System behavior

When locked:

- New purchases should be declined according to processor rules.
- Account remains open.
- Other cards remain unaffected.

Unlock should generally require an authenticated authorized user.

---

# 17. Replace Card

Replacement should support multiple scenarios.

### Reasons

- Lost.
- Stolen.
- Damaged.
- Compromised.
- Expiring.
- Incorrect cardholder name.

### Workflow

Customer selects:

1. Card.
2. Replacement reason.
3. Shipping address.
4. Shipping speed.
5. Confirmation.

System should show:

- Existing card status.
- Replacement card order.
- Estimated delivery.
- Shipment/tracking status where available.

---

# 18. Virtual Cards

Virtual cards provide controlled digital payment credentials.

### Capabilities

Create cards for:

- Individual employees.
- Vendors.
- Projects.
- Purchase orders.
- Specific transactions.

### Controls

Each virtual card can have:

- Maximum amount.
- Expiration date.
- Usage count.
- Merchant restriction.
- Category restriction.

Possible configurations:

- Single-use.
- Multi-use.
- Fixed vendor.
- Fixed amount.
- Time limited.

Virtual cards provide stronger purchasing controls than sharing a physical business card.

---

# 19. Transaction Management

The transaction center should provide a searchable ledger of card activity.

Each transaction should include:

- Merchant.
- Amount.
- Transaction date.
- Posting date.
- Cardholder.
- Card ending digits.
- Merchant category.
- Location.
- Authorization status.
- Expense category.
- Receipt status.

### Transaction statuses

- Pending.
- Posted.
- Declined.
- Reversed.
- Refunded.
- Disputed.

---

# 20. Transaction Search and Filtering

Large businesses may have thousands of transactions, so filtering is critical.

Allow search by:

- Merchant.
- Employee.
- Card.
- Department.
- Cost center.
- Amount.
- Date.
- Category.
- Status.
- Transaction ID.

### Advanced filters

Examples:

- Amount > $5,000.
- International transactions.
- Missing receipts.
- Transactions over policy.
- Weekend purchases.
- Card-not-present transactions.

Users should be able to save commonly used filters.

---

# 21. Transaction Details

Selecting a transaction should open a detailed record.

Display:

- Merchant name.
- Merchant ID.
- Merchant category.
- Amount.
- Currency.
- Exchange rate.
- Authorization timestamp.
- Posting timestamp.
- Cardholder.
- Card.
- Location.
- Expense category.
- Receipt.
- Notes.
- Dispute status.

### Actions

The user may:

- Add notes.
- Add receipt.
- Categorize.
- Mark business purpose.
- Dispute transaction.
- Report fraud.

---

# 22. Expense Categorization

The solution should allow transactions to be assigned accounting categories.

Examples:

- Airfare.
- Lodging.
- Meals.
- Fuel.
- Office supplies.
- Software.
- Consulting.
- Advertising.
- Utilities.
- Telecommunications.

Users could also map categories to:

- GL codes.
- Cost centers.
- Departments.
- Projects.
- Customers.

Automatic category suggestions can be based on merchant category codes.

---

# 23. Receipt Management

Receipt capture simplifies expense reconciliation.

### Upload methods

Support:

- PDF.
- JPG.
- PNG.
- Mobile photo.
- Email forwarding.
- Expense-app integration.

### Receipt information

Extract or capture:

- Merchant.
- Date.
- Amount.
- Tax.
- Currency.
- Line items.

The receipt should be associated with the corresponding card transaction.

---

# 24. Dispute Transaction

Customers should be able to dispute posted transactions.

### Reasons

- Unauthorized.
- Duplicate.
- Incorrect amount.
- Merchandise not received.
- Services not provided.
- Returned goods not credited.
- Canceled transaction.
- Incorrect currency.

### Workflow

1. Select transaction.
2. Select dispute reason.
3. Answer guided questions.
4. Upload evidence.
5. Submit.
6. Receive dispute number.
7. Track investigation.

---

# 25. Fraud Reporting

Fraud reporting differs from ordinary merchant disputes.

### Customer options

Users should be able to:

- Identify unauthorized transactions.
- Lock affected card.
- Report stolen credentials.
- Request replacement.
- Review recent activity.

### Backend process

Create:

- Fraud case.
- Associated transactions.
- Risk priority.
- Investigator assignment.
- Card replacement workflow.

Critical activity can generate immediate notifications.

---

# 26. Statements

The Statements section should provide historical billing records.

Each statement should contain:

- Opening balance.
- Payments.
- Credits.
- Purchases.
- Fees.
- Interest.
- Closing balance.
- Minimum payment.
- Due date.

### Statement library

Customers should be able to:

- View online.
- Download PDF.
- Search by year.
- Search by billing period.

Retention duration should follow organizational/legal requirements.

---

# 27. Payments

Customers should be able to make payments directly from the account dashboard.

### Payment choices

- Minimum due.
- Statement balance.
- Current balance.
- Custom amount.

### Funding sources

Potentially:

- Linked checking account.
- Linked savings account.
- ACH.
- Internal deposit account.

### Payment lifecycle

Statuses:

- Scheduled.
- Processing.
- Completed.
- Returned.
- Failed.
- Canceled.

---

# 28. AutoPay

AutoPay allows businesses to automatically pay balances.

Options can include:

- Minimum due.
- Statement balance.
- Fixed amount.
- Custom policy.

Display:

- Funding account.
- Payment rule.
- Next payment date.
- Next payment amount.
- Enrollment status.

Users should be able to pause or cancel AutoPay.

---

# 29. Payment History

Provide an auditable payment ledger.

Fields:

- Payment date.
- Submission timestamp.
- Amount.
- Funding source.
- Confirmation number.
- Status.
- Posted date.

Filtering should support:

- Date range.
- Amount.
- Status.
- Account source.

---

# 30. Rewards

Rewards dashboards should give businesses clear visibility into earned benefits.

Display:

- Available points.
- Pending points.
- Cashback.
- Miles.
- Expiring rewards.
- Recent earning activity.

### Reward earning details

For each transaction show:

- Base points.
- Bonus category.
- Promotional points.
- Final earned amount.

Remember that the Xenhey prototype explicitly notes that displayed rewards/rates are representative rather than guaranteed. :chatgpt-content-reference{index="3"}

---

# 31. Rewards Redemption

Businesses should be able to redeem accumulated benefits.

Options could include:

- Statement credit.
- Cashback.
- Travel.
- Gift cards.
- Merchandise.
- Partner transfer.

The UI should show:

- Available balance.
- Redemption rate.
- Minimum redemption.
- Estimated value.
- Confirmation.

Maintain a redemption history.

---

# 32. Business Reporting

Reporting should provide management-level insight into spending.

Reports might include:

- Spend by month.
- Spend by employee.
- Spend by department.
- Spend by category.
- Spend by vendor.
- Spend by project.
- Top merchants.
- Largest transactions.
- International spending.
- Credit utilization.

### Management dashboards

Examples:

**Monthly Spend Trend**

Jan → $85K  
Feb → $91K  
Mar → $104K

**Top Departments**

Operations — 38%  
Sales — 27%  
IT — 19%

---

# 33. Download / Export

Customers should be able to export financial data.

Formats:

- CSV.
- XLSX.
- PDF.
- JSON for APIs.
- Accounting formats where required.

Exports could include:

- Transactions.
- Statements.
- Payments.
- Employee cards.
- Expense reports.
- Rewards.

Users should choose a date range and filters before export.

---

# 34. Accounting Integration

Business card activity can integrate directly with accounting or ERP platforms.

Potential targets include:

- QuickBooks.
- Xero.
- NetSuite.
- SAP.
- Oracle.
- Microsoft Dynamics.

### Integration functions

Synchronize:

- Transactions.
- Accounts.
- Employees.
- Cost centers.
- GL codes.
- Receipts.

This reduces manual accounting reconciliation.

---

# 35. Alerts and Notifications

Alerts should be configurable by account and user.

Examples:

### Spending

- Transaction above $1,000.
- Employee reaches 80% of limit.
- International purchase.
- Declined purchase.

### Account

- Credit utilization above 75%.
- Payment due.
- Payment received.
- Statement available.

### Security

- Card locked.
- Password changed.
- Suspicious transaction.
- New administrator added.

Delivery channels:

- Email.
- SMS.
- Push notification.
- In-app notification.

---

# 36. Business User Management

Business owners should be able to delegate portal access.

Each user has:

- Name.
- Email.
- Role.
- Status.
- Last login.
- Assigned accounts.
- Assigned cards.

### Actions

Administrators may:

- Invite user.
- Disable user.
- Reactivate user.
- Change role.
- Reset access.
- Remove user.

---

# 37. Role-Based Access Control

RBAC prevents every business user from having unlimited access.

Example roles:

### Business Owner

Full access.

### Card Administrator

Manage cards and limits.

### Finance Manager

Transactions, payments, statements, reporting.

### Auditor

Read-only.

### Employee

Own card and transactions.

### Custom Role

Enterprise organizations could select individual permissions.

Sensitive actions such as limit increases might require elevated privileges or approval.

---

# 38. Profile Management

Businesses need a centralized profile.

Manage:

- Legal address.
- Mailing address.
- Primary contact.
- Phone.
- Email.
- Business website.
- Industry.
- Contact preferences.

Certain legal or ownership changes may require additional verification rather than instant self-service updates.

---

# 39. Secure Messaging / Support

Provide authenticated communications between business customers and servicing personnel.

Customers should be able to create requests for:

- Card issue.
- Payment problem.
- Fraud question.
- Dispute question.
- Statement question.
- Account update.
- Limit increase.

Each conversation can include:

- Case number.
- Status.
- Assigned team.
- Message history.
- Attachments.

---

# 40. Card Operations / Admin Dashboard

The separate Admin Dashboard is explicitly present in the Xenhey prototype as **Business Credit Cards / Admin — Card Operations**. :chatgpt-content-reference{index="4"}

The operations dashboard should show:

- New applications.
- Pending applications.
- Manual reviews.
- Approved applications.
- Declined applications.
- Active accounts.
- Active cards.
- Suspended cards.
- Fraud cases.
- Disputes.
- Customer service cases.

### Operational metrics

Examples:

- Applications today.
- Average approval time.
- Cards activated today.
- Fraud cases opened.
- Disputes awaiting review.
- Total credit exposure.

---

# 41. Admin Application Queue

Operations personnel need a queue to manage incoming applications.

Columns should include:

- Application ID.
- Business.
- Applicant.
- Product.
- Requested credit.
- Submission date.
- Verification result.
- Risk indicator.
- Current status.
- Assigned analyst.

### Filters

Allow:

- New.
- Pending.
- High risk.
- Missing documents.
- Manual review.
- Escalated.

Queue assignment should support team ownership.

---

# 42. Admin Application Review

Selecting an application gives the analyst a complete case file.

Sections include:

- Business information.
- Applicant.
- Beneficial owners.
- Financials.
- Requested limit.
- Verification results.
- Supporting documents.
- Risk indicators.

### Actions

Analyst can:

- Approve.
- Decline.
- Request documents.
- Refer to underwriting.
- Escalate.
- Place on hold.

Every decision should create an audit record.

---

# 43. Document Review

Administrative users need document verification tools.

Documents may include:

- Formation documents.
- Business license.
- Tax documents.
- Financial statements.
- Bank statements.
- Proof of address.
- Ownership documents.

### Reviewer controls

Each document can receive:

- Accepted.
- Rejected.
- Unreadable.
- Expired.
- Additional information required.

Comments should explain why a document failed verification.

---

# 44. Identity / Business Verification

A verification workspace should aggregate external and internal verification results.

Display:

- Business-name match.
- EIN match.
- Address match.
- Entity status.
- Representative identity status.
- Beneficial-owner status.
- Fraud-screening result.
- Sanctions-screening result.

Analysts should be able to distinguish system-generated results from manual overrides.

---

# 45. Underwriting

Underwriting determines whether credit can be extended and under what conditions.

### Information presented

- Requested limit.
- Revenue.
- Existing debt.
- Existing institutional relationship.
- Credit information.
- Risk indicators.
- Historical business information.

### Decision support

System-generated recommendations could include:

- Suggested limit.
- Risk grade.
- Required conditions.
- Additional verification requirement.

Final decisions should follow the financial institution's approved underwriting policy.

---

# 46. Credit Decision

The formal credit-decision screen captures the underwriting outcome.

Decision options:

- Approve as requested.
- Approve at lower limit.
- Approve at higher limit if permitted.
- Conditional approval.
- Pending documentation.
- Decline.
- Refer.

### Decision information

Capture:

- Approved limit.
- Decision reason.
- Analyst.
- Approver.
- Timestamp.
- Conditions.

Sensitive adverse-action communications should follow applicable requirements.

---

# 47. Credit Limit Management

Post-origination credit limits may need adjustment.

### Customer request

Customer submits:

- Requested limit.
- Business reason.
- Updated revenue.
- Supporting information.

### Admin actions

Operations can:

- Approve.
- Decline.
- Counteroffer.
- Request information.

Keep complete history of:

Previous limit → requested limit → approved limit.

---

# 48. Business Account Administration

Operations personnel need an account servicing workspace.

Display:

- Business identity.
- Credit line.
- Available credit.
- Current balance.
- Account status.
- Cardholders.
- Cards.
- Payments.
- Transactions.
- Fraud cases.
- Disputes.
- Support history.

This becomes the operational system-of-record view for the account.

---

# 49. Admin Card Management

Authorized operations personnel should manage physical and virtual cards.

Admin actions include:

- Issue.
- Activate.
- Suspend.
- Lock.
- Unlock.
- Replace.
- Close.
- Modify limit.
- Change cardholder.

Every card-state change should record:

- Operator.
- Reason.
- Timestamp.
- Previous state.
- New state.

---

# 50. Fraud Operations

Fraud analysts need a specialized queue.

Fields might include:

- Fraud case ID.
- Account.
- Card.
- Transactions.
- Risk score.
- Alert reason.
- Amount at risk.
- Investigator.
- Status.

### Investigation workflow

New → Assigned → Investigating → Customer Contact → Decision → Resolved.

Possible outcomes:

- Confirmed fraud.
- False positive.
- Customer authorized.
- Merchant issue.
- Escalation.

---

# 51. Dispute Administration

Dispute specialists require a dedicated workflow.

Display:

- Dispute number.
- Transaction.
- Customer reason.
- Documentation.
- Merchant information.
- Amount.
- Status.
- Key dates.

### Operations actions

- Review submission.
- Request supporting documents.
- Record provisional credit.
- Update investigation.
- Resolve case.
- Notify customer.

---

# 52. Case Management

A generic case-management engine can support multiple servicing processes.

Case types:

- Fraud.
- Dispute.
- Lost card.
- Payment problem.
- Account maintenance.
- Limit request.
- Complaint.
- Technical support.

Each case contains:

- Case number.
- Customer.
- Priority.
- Category.
- Assigned team.
- Assigned user.
- SLA.
- Notes.
- Attachments.
- Status.

---

# 53. Customer 360 View

Customer 360 gives operations a single consolidated view of a business relationship.

Display:

### Business

- Business profile.
- Contacts.
- Owners.

### Products

- Credit cards.
- Deposits.
- Loans.
- Merchant services.

### Activity

- Transactions.
- Payments.
- Cases.
- Communications.

### Risk

- Fraud alerts.
- Delinquency.
- Disputes.

This minimizes switching between multiple applications.

---

# 54. Search

Admin users need a global search function.

Searchable identifiers:

- Business name.
- EIN where authorized.
- Account number.
- Card last four.
- Customer name.
- Application ID.
- Transaction ID.
- Case ID.
- Dispute ID.

Search should respect RBAC so users cannot retrieve information they are not permitted to see.

---

# 55. Administrative Reporting

Operations leadership needs reporting beyond customer-facing spend analysis.

Examples:

### Application reporting

- Application volume.
- Approval rates.
- Decline rates.
- Average decision time.
- Manual review rate.

### Card operations

- New cards.
- Replacement cards.
- Suspended cards.
- Activated cards.

### Risk

- Fraud volume.
- Fraud losses.
- Disputes.
- Chargebacks.

### Financial

- Outstanding balances.
- Total credit.
- Utilization.

---

# 56. Audit Trail

The system should record all significant sensitive actions.

Audit events can include:

- Login.
- Role changes.
- Application decisions.
- Credit-limit changes.
- Card locks.
- Payment changes.
- Account changes.
- Fraud decisions.
- Administrative overrides.

Capture:

- User.
- Role.
- Action.
- Object.
- Previous value.
- New value.
- Timestamp.
- Correlation ID.

Audit records should be protected against unauthorized alteration.

---

# 57. Admin Role Management

Administrative roles should follow least privilege.

Example roles:

- Customer Service Agent.
- Card Operations Specialist.
- Underwriter.
- Fraud Analyst.
- Dispute Specialist.
- Compliance Analyst.
- Supervisor.
- System Administrator.

Example:

A Fraud Analyst may investigate transactions but should not necessarily be allowed to modify underwriting decisions.

---

# 58. Product Administration

Authorized product managers should be able to maintain the Business Credit Card catalog.

Manage:

- Product name.
- Description.
- Card artwork.
- Annual fee.
- Pricing.
- Rewards.
- Benefits.
- Eligibility.
- Application availability.
- Employee-card options.
- Product status.

### Lifecycle

Products can be:

- Draft.
- Pending approval.
- Published.
- Suspended.
- Retired.

Changes should preferably be versioned.

---

# 59. Configuration

Not every rule should require software deployment.

Administrative configuration can include:

- Application statuses.
- Case statuses.
- Merchant categories.
- Spending thresholds.
- Alert thresholds.
- Fraud rules.
- Dispute reasons.
- Notification templates.
- Document types.
- Workflow assignments.

Configuration changes should have governance and audit tracking.

---

# 60. Financial Product Catalog Integration

The Xenhey prototype includes navigation to a broader **Financial Product Catalog** alongside Customer Flow and Admin Flow. :chatgpt-content-reference{index="5"}

Business Credit Cards can therefore be integrated with products such as:

- Business Checking.
- Business Savings.
- Merchant Services.
- Business Loans.
- Lines of Credit.
- Treasury Management.
- Commercial Lending.
- Insurance.

### Benefits

The institution receives a unified customer journey rather than isolated product applications.

For example:

**Business Checking → Business Credit Card → Merchant Services → Business Line of Credit**

---

# 61. Cross-Sell / Next-Best Product

Cross-sell capabilities should recommend related products based on context rather than random advertising.

Examples:

A retailer using Business Credit Cards may also benefit from Merchant Services.

A company with high recurring vendor spend may be shown purchasing-card options.

A company maintaining substantial balances may be shown Treasury Management.

### Recommendation inputs

Possible factors:

- Existing products.
- Business size.
- Industry.
- Transaction activity.
- Account tenure.
- Customer-selected interests.

Recommendations should be clearly distinguishable from required account actions.

---

# 62. Security Features

Security must be built across customer and admin experiences.

### Authentication

Support:

- Secure login.
- MFA.
- Session management.
- Risk-based authentication where appropriate.

### Authorization

Use:

- RBAC.
- Least privilege.
- Separation of duties.
- Privileged access controls.

### Data protection

Protect:

- PAN/card data.
- Personal data.
- Financial information.
- Credentials.

Use:

- Encryption in transit.
- Encryption at rest.
- Tokenization/masking.
- Secure secret management.

### Monitoring

Detect:

- Suspicious login.
- Privilege escalation.
- Repeated authentication failures.
- Unusual administrative activity.

---

# 63. Compliance Capabilities

A financial-card solution needs a configurable compliance architecture.

Relevant areas may include, depending on issuer, jurisdiction, and implementation:

- PCI DSS.
- KYC/CIP.
- AML processes.
- Sanctions controls.
- Privacy obligations.
- Record retention.
- Electronic communications/disclosures.
- Auditability.
- Segregation of duties.

### Compliance evidence

Systems should maintain:

- Accepted disclosures.
- Identity-verification results.
- Application decisions.
- Administrative actions.
- Role changes.
- Transaction audit records.
- Case histories.

Compliance requirements should be validated against the institution's legal, risk, and compliance framework rather than inferred only from product design.

---

# 64. UX / Wireframe Requirements

This final feature turns the functional requirements into an implementable screen inventory.

For the Xenhey Business Credit Cards solution, I would organize the wireframes into five major journeys.

### A. Acquisition and application

1. Business Credit Card Landing
2. Product Catalog
3. Product Details
4. Compare Cards
5. Application Start
6. Business Information
7. Ownership Information
8. Authorized Representative
9. Financial Information
10. Employee Cards
11. Supporting Documents
12. Terms and Disclosures
13. Review Application
14. Application Confirmation
15. Application Status

### B. Customer servicing

16. Customer Dashboard
17. Account Overview
18. Card List
19. Card Details
20. Add Employee
21. Employee Details
22. Spending Controls
23. Virtual Cards
24. Card Activation
25. Replace Card
26. Transactions
27. Transaction Detail
28. Receipt Upload
29. Expense Categorization
30. Statements
31. Payments
32. AutoPay
33. Payment History
34. Rewards
35. Rewards Redemption
36. Reports
37. Alerts
38. Business Profile
39. User Management
40. Secure Messages

### C. Fraud and disputes

41. Report Fraud
42. Suspicious Transactions
43. Fraud Case Status
44. Start Dispute
45. Dispute Details
46. Dispute Status

### D. Administrative operations

47. Admin Dashboard
48. Application Queue
49. Application Review
50. Document Review
51. Verification Results
52. Underwriting
53. Credit Decision
54. Account Administration
55. Card Administration
56. Fraud Queue
57. Fraud Investigation
58. Dispute Queue
59. Dispute Investigation
60. Case Management
61. Customer 360
62. Global Search

### E. Administration and governance

63. Administrative Reports
64. Product Administration
65. Configuration
66. Role Management
67. Audit Logs
68. Product Catalog Management.

So while the original functional list contains **64 major capabilities**, a production-ready UX decomposition naturally results in roughly **65–70 individual wireframes/screens**, because several larger capabilities—fraud, disputes, applications, and administration—require multiple screens.

---

# Recommended End-to-End Navigation

A coherent customer journey would be:

**Financial Product Catalog**  
→ **Business Credit Cards**  
→ **Compare Cards**  
→ **Select Product**  
→ **Business Application**  
→ **Business Verification**  
→ **Underwriting**  
→ **Approval**  
→ **Card Issuance**  
→ **Card Activation**  
→ **Customer Dashboard**  
→ **Employee Cards**  
→ **Transactions**  
→ **Payments / Statements / Rewards / Reporting**

The operational journey would be:

**Admin Dashboard**  
→ **Application Queue**  
→ **Application Review**  
→ **Verification**  
→ **Underwriting**  
→ **Credit Decision**  
→ **Account Creation**  
→ **Card Operations**  
→ **Customer 360**  
→ **Fraud / Dispute / Case Management**  
→ **Reporting / Audit**

That architecture preserves the core distinction already visible in Xenhey: a **Business Customer dashboard/card-account experience** on one side and a **Card Operations Admin Dashboard** on the other, connected through the Business Credit Cards product and broader Financial Product Catalog. :chatgpt-content-reference{index="6"}
