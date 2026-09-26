I reviewed the Xenhey **Personal Credit Cards** prototype. The current experience is organized around two major personas: **Cardholder / Customer Flow** and **Issuer Operations / Admin Flow**, with a shared **Financial Product Catalog**. The prototype also clearly identifies itself as using synthetic sample data and not guaranteeing approval, APR, credit limits, fees, or rewards. :chatgpt-content-reference{index="0"}

Below is a more complete feature model you can use to expand this into a realistic **bank-grade Personal Credit Card platform**.

## 1. Credit Card Product Catalog

The catalog should support multiple card products rather than treating “credit card” as one generic product.

Recommended card types include:

- Cash-back card
- Travel rewards card
- Points rewards card
- Airline co-branded card
- Hotel co-branded card
- Student credit card
- Secured credit card
- Credit-builder card
- Low-interest card
- Balance-transfer card
- Premium rewards card
- No-annual-fee card
- Retail/private-label card
- Small-balance starter card
- Relationship banking card
- High-net-worth / premium relationship card

Each product should expose:

- Product name
- Card artwork
- Card network
- Annual fee
- Purchase APR
- Balance-transfer APR
- Cash-advance APR
- Penalty APR
- Introductory APR
- Introductory APR period
- Foreign transaction fee
- Balance-transfer fee
- Cash-advance fee
- Late-payment fee
- Returned-payment fee
- Minimum credit line
- Maximum credit line
- Minimum recommended credit score
- Reward rate
- Welcome bonus
- Spend requirement
- Bonus period
- Travel benefits
- Purchase protection
- Extended warranty
- Rental-car coverage
- Cell-phone protection
- Fraud protection
- Eligibility requirements
- Terms and conditions
- Product disclosures

### Additional recommendation

Add a **Compare Cards** feature allowing customers to select two to four cards and compare:

- Annual fee
- APR
- Rewards
- Welcome bonus
- Travel features
- Credit requirements
- Foreign transaction fees
- Balance-transfer offers
- Recommended customer profile

---

# 2. Credit Card Recommendation Engine

Before applying, customers should be able to answer a short needs-assessment questionnaire.

Questions can include:

- Primary reason for obtaining the card
- Average monthly spending
- Travel frequency
- International travel frequency
- Grocery spending
- Dining spending
- Gas spending
- Streaming spending
- Online shopping
- Preferred rewards
- Existing credit-card debt
- Interest in balance transfers
- Estimated credit score range
- Preference for annual-fee versus no-fee products

The system can generate:

**Recommended for you**

For example:

- Best suited for travel spending
- Strong fit for cash-back users
- Useful for balance consolidation
- Appropriate for credit-building
- Premium rewards option

The recommendation should remain educational rather than imply approval.

---

# 3. Prequalification

A strong addition would be a **prequalification flow** before the complete application.

Customer enters:

- Name
- Address
- Date of birth
- Last four digits of SSN
- Income range
- Housing status
- Monthly housing payment

Possible outcomes:

- Prequalified products available
- Additional information required
- No current offers

The system should clearly distinguish:

**Prequalification**

from

**Final credit approval**

---

# 4. Credit Card Application

The full application should contain a detailed multi-step intake process.

## Step 1 — Personal Information

Capture:

- First name
- Middle name
- Last name
- Suffix
- Date of birth
- SSN/TIN
- Citizenship
- Residency status
- Country of residence
- Mobile phone
- Email address

## Step 2 — Address

Capture:

- Residential address
- Mailing address
- Years at address
- Housing status
- Rent
- Own
- Living with family
- Other
- Monthly housing payment

## Step 3 — Employment

Capture:

- Employment status
- Employer
- Occupation
- Years employed
- Work phone

Employment categories:

- Employed
- Self-employed
- Retired
- Student
- Unemployed
- Other

## Step 4 — Income

Capture:

- Annual gross income
- Additional income
- Income type
- Monthly housing payment
- Optional assets

## Step 5 — Card Preferences

Allow selection of:

- Preferred card design
- Digital statements
- Authorized user
- Balance transfer
- Requested credit line, where applicable

## Step 6 — Disclosures

Display:

- APR
- Fees
- Privacy disclosure
- Credit authorization
- Terms
- Electronic communication consent

Require explicit acknowledgment.

## Step 7 — Review

Display an application summary before submission.

## Step 8 — Submission

Generate:

- Application ID
- Submission timestamp
- Application status
- Next steps

---

# 5. Application Status Tracking

The customer dashboard should support:

- Application submitted
- Identity verification pending
- Credit review
- Additional documents required
- Manual review
- Approved
- Declined
- Approved with modified terms
- Card being produced
- Card shipped
- Card delivered

Recommended addition:

### Application timeline

Example:

**Application Submitted → Identity Verified → Credit Review → Approved → Card Production → Shipped**

---

# 6. Document Upload

Customers may need to provide:

- Driver's license
- Passport
- Permanent resident card
- Proof of address
- Pay stub
- W-2
- Tax return
- Bank statement

Features should include:

- Drag-and-drop upload
- Mobile camera capture
- File validation
- Document preview
- Upload status
- Resubmission request
- Document expiration detection

---

# 7. Identity Verification

The platform should support:

- Identity verification
- Address validation
- SSN validation
- Phone verification
- Email verification
- OTP verification
- Device fingerprinting
- Knowledge-based verification where permitted
- Document verification
- Selfie/liveness verification where appropriate

---

# 8. Customer Credit Card Dashboard

The existing Xenhey customer experience already has a **Cardholder dashboard** concept. :chatgpt-content-reference{index="1"}

Expand it into a complete financial dashboard.

Show:

- Current balance
- Available credit
- Credit limit
- Pending balance
- Statement balance
- Minimum payment
- Payment due date
- Available cash advance
- Reward balance
- Credit utilization
- Recent transactions
- Upcoming payments
- Active promotional offers

---

# 9. Account Summary

Customers should see:

**Current Balance**

**Statement Balance**

**Available Credit**

**Credit Limit**

Example:

- Credit Limit: $10,000
- Current Balance: $2,350
- Available Credit: $7,650
- Utilization: 23.5%

Also show:

- Payment due
- Minimum due
- Statement closing date
- Next statement date

---

# 10. Transaction Management

Transaction functionality should be extensive.

Customers should be able to:

- View transactions
- Search transactions
- Filter transactions
- Sort transactions
- Categorize transactions
- Download transactions
- Dispute transactions
- Add notes
- Flag suspicious transactions

Filters:

- Date
- Merchant
- Amount
- Category
- Cardholder
- Transaction status
- Location

Transaction statuses:

- Pending
- Posted
- Reversed
- Refunded
- Disputed

---

# 11. Merchant Details

Selecting a transaction should display:

- Merchant name
- Merchant category
- Transaction date
- Posting date
- Amount
- Location
- Payment method
- Card used
- Transaction ID

Recommended enhancement:

Display merchant location on a map.

---

# 12. Spend Categorization

Automatically categorize transactions into:

- Groceries
- Dining
- Travel
- Gas
- Entertainment
- Shopping
- Healthcare
- Utilities
- Subscription services
- Transportation
- Education
- Other

Allow customers to change categories.

---

# 13. Spending Analytics

Add visual reporting for:

- Monthly spend
- Weekly spend
- Category spend
- Merchant spend
- Year-over-year spend
- Average transaction
- Recurring transactions

Charts could show:

**Dining — 18%**

**Groceries — 22%**

**Travel — 12%**

**Shopping — 20%**

**Other — 28%**

---

# 14. Spending Budget

Allow customers to set category budgets.

For example:

Groceries  
$650 / $800

Dining  
$410 / $500

Travel  
$1,400 / $2,000

Send alerts at:

- 50%
- 75%
- 90%
- 100%

---

# 15. Credit Utilization Monitoring

Show credit utilization prominently.

Example:

**$2,350 used of $10,000**

**23.5% utilization**

Provide historical utilization.

Recommended features:

- Utilization alerts
- High-utilization notification
- Payment recommendation calculator

---

# 16. Payments

Customers should be able to:

- Make payment
- Schedule payment
- Cancel scheduled payment
- Edit payment
- Make same-day payment
- Pay minimum
- Pay statement balance
- Pay current balance
- Pay custom amount

Funding sources:

- Checking account
- Savings account
- External bank account

---

# 17. Autopay

Autopay options should include:

- Minimum payment
- Statement balance
- Current balance
- Fixed amount
- Percentage of balance

Allow customers to select:

- Payment account
- Payment date
- Backup account

---

# 18. Payment History

Show:

- Payment date
- Payment amount
- Payment account
- Confirmation number
- Status

Statuses:

- Scheduled
- Processing
- Completed
- Returned
- Cancelled

---

# 19. Statements

Customers should be able to access:

- Monthly statements
- Annual statements
- Tax documents if applicable
- Disclosures
- Notices

Functions:

- View
- Download PDF
- Search
- Filter by year
- Paperless enrollment

---

# 20. Card Controls

A modern credit-card application should give customers direct control over their card.

Include:

- Lock card
- Unlock card
- Report lost card
- Report stolen card
- Replace damaged card
- Request replacement card

---

# 21. Transaction Controls

Allow cardholders to control where a card can be used.

Options:

- ATM transactions
- Online transactions
- International transactions
- Contactless transactions
- Cash advances

Advanced controls:

- Merchant categories
- Geographic regions
- Spending thresholds

---

# 22. Virtual Credit Card

Add:

- Instant virtual card
- Virtual card number
- Expiration
- CVV
- Copy card number
- Lock virtual card
- Delete virtual card

Advanced feature:

**Merchant-specific virtual numbers**

---

# 23. Digital Wallet

Support provisioning to:

- Apple Pay
- Google Pay
- Samsung Wallet

Show:

- Wallet status
- Device
- Token status

---

# 24. Card Activation

Activation flow:

1. Enter card information.
2. Verify identity.
3. Confirm CVV.
4. Create PIN.
5. Activate card.
6. Offer digital wallet enrollment.

---

# 25. PIN Management

Customers should be able to:

- Create PIN
- Change PIN
- Request PIN reminder/reset

---

# 26. Replacement Card

Replacement reasons:

- Lost
- Stolen
- Damaged
- Fraud
- Never received
- Expiring card

Show:

- Replacement status
- Shipping status
- Estimated delivery

---

# 27. Credit Limit Increase

Customers can request:

- Temporary increase
- Permanent increase

Capture:

- Current income
- Housing expense
- Employment
- Requested limit

Track:

**Submitted → Review → Approved/Declined**

---

# 28. Rewards Dashboard

Show:

- Available points
- Cash-back balance
- Points earned this month
- Pending rewards
- Rewards expiring
- Redemption history

---

# 29. Rewards Redemption

Allow redemption for:

- Statement credit
- Cash deposit
- Gift cards
- Travel
- Merchandise
- Experiences

---

# 30. Rewards Activity

Show points associated with each transaction.

Example:

Restaurant purchase  
$120  
3X points  
360 points earned

---

# 31. Promotional Offers

Display targeted offers such as:

- 5% dining cash back
- 3X travel points
- Merchant discount
- 0% balance-transfer offer

Allow:

**Activate Offer**

---

# 32. Balance Transfers

Balance-transfer workflow should allow customers to enter:

- Creditor name
- Account number
- Transfer amount

Show:

- Transfer fee
- Promotional APR
- Expiration date

Status:

**Submitted → Processing → Completed**

---

# 33. Cash Advance

Show:

- Available cash advance
- Cash-advance APR
- Cash-advance fee

Provide appropriate warnings because costs differ from regular purchases.

---

# 34. Authorized Users

Customers should be able to:

- Add authorized user
- Remove authorized user
- Freeze authorized-user card
- Set spending limit
- View spending

Capture:

- Name
- DOB
- Relationship
- Address

---

# 35. Dispute Center

Transaction disputes should support:

- Transaction selection
- Dispute reason
- Supporting documents
- Customer explanation
- Confirmation

Reasons:

- Card not present
- Duplicate charge
- Wrong amount
- Product not received
- Refund not received
- Fraudulent transaction

---

# 36. Dispute Tracking

Display:

**Opened → Under Review → Merchant Contacted → Temporary Credit → Resolved**

Show:

- Case ID
- Disputed amount
- Dates
- Messages
- Supporting documents

---

# 37. Fraud Center

Create a centralized fraud experience.

Features:

- Report suspicious transaction
- Confirm transaction
- Report stolen card
- Freeze card
- Replace card
- View fraud cases

---

# 38. Real-Time Fraud Alerts

Notifications can ask:

**Was this you?**

User responses:

**Yes**

**No**

Selecting **No** can initiate:

- Card freeze
- Fraud case
- Card replacement

---

# 39. Notification Center

Support alerts through:

- Push
- SMS
- Email
- In-app notifications

Examples:

- Transaction over $500
- International transaction
- Online transaction
- Payment due
- Payment received
- Payment failed
- Card declined
- Card used
- Balance threshold
- Credit-limit threshold
- Reward earned
- Fraud alert

---

# 40. Credit Score

Offer optional credit-score monitoring.

Display:

- Current score
- Historical trend
- Score factors
- Credit utilization
- Payment history

---

# 41. Credit Education

Provide content explaining:

- Credit scores
- Credit utilization
- Payment history
- Hard inquiries
- APR
- Minimum payments
- Interest calculation

---

# 42. Interest Calculator

Allow customers to simulate:

**Current balance**

**APR**

**Monthly payment**

Then show estimated:

- Payoff time
- Interest paid

---

# 43. Payoff Planner

Allow customers to choose:

**Pay off in 3 months**

**6 months**

**12 months**

and calculate a suggested monthly payment.

---

# 44. Recurring Subscription Detection

Identify recurring charges such as:

- Netflix
- Spotify
- Gym membership
- Cloud storage

Show:

**Recurring Monthly Expenses**

This is useful for spend management.

---

# 45. Travel Management

Allow customers to:

- Set travel notification
- Confirm destination
- Confirm dates
- Enable international usage

Modern fraud engines may not require travel notices operationally, but it remains a useful customer-experience feature.

---

# 46. Customer Profile

Manage:

- Name
- Address
- Phone
- Email
- Employment
- Income
- Preferred language
- Communication preferences

Sensitive changes should require additional authentication.

---

# 47. Security Settings

Include:

- Password management
- MFA
- Passkeys
- Trusted devices
- Active sessions
- Login history

Allow:

**Sign out all devices**

---

# 48. Secure Messaging

Customers should communicate securely with the issuer.

Message categories:

- Billing
- Fraud
- Rewards
- Payments
- Credit limit
- Application
- Disputes

---

# 49. Help Center

Provide searchable support for:

- Payments
- Rewards
- Fraud
- Statements
- Card replacement
- APR
- Fees
- Travel
- Digital wallets

---

# 50. AI Financial Assistant

One of the strongest additions for the Xenhey prototype would be an AI assistant grounded in the customer's account data.

Examples:

**“How much did I spend on restaurants last month?”**

**“Why is my minimum payment higher?”**

**“What subscriptions am I paying for?”**

**“How many reward points did I earn from travel?”**

**“What would I need to pay monthly to clear this balance in six months?”**

The assistant should not independently execute sensitive account changes without explicit confirmation.

---

# Issuer / Admin Operations

Xenhey already provides a dedicated **Issuer Operations / Admin Dashboard**, which is the right foundation for the operational side of the platform. :chatgpt-content-reference{index="2"}

## 51. Admin Dashboard

Show enterprise KPIs:

- Active accounts
- Applications today
- Approval rate
- Decline rate
- Pending reviews
- Total credit exposure
- Average credit limit
- Outstanding balances
- Delinquency rate
- Fraud cases
- Disputes
- Payment volume

---

# 52. Application Management

Operations users should be able to:

- Search applications
- Review application
- Verify documents
- Review credit decision
- Request more information
- Approve
- Decline
- Escalate

---

# 53. Underwriting Workbench

Show:

- Applicant profile
- Income
- Debt obligations
- Credit score
- Credit history
- Existing exposure
- Fraud score
- Risk score

Recommended decision statuses:

- Auto-approved
- Auto-declined
- Manual review

---

# 54. Credit Decision Engine

Rules can evaluate:

- Credit score
- Debt-to-income
- Income
- Delinquencies
- Credit history
- Utilization
- Recent inquiries
- Existing issuer exposure

Keep decision rules version-controlled.

---

# 55. Credit Limit Management

Issuer users should manage:

- Initial credit limit
- Automatic increases
- Customer-requested increases
- Credit-line decreases
- Temporary increases

---

# 56. Account Management

Admin users should view:

- Account profile
- Cards
- Transactions
- Payments
- Statements
- Rewards
- Authorized users
- Fraud cases
- Disputes
- Communications

---

# 57. Customer 360 View

This would significantly improve the admin experience.

One page should show:

**Customer**

→ Accounts  
→ Cards  
→ Transactions  
→ Applications  
→ Payments  
→ Rewards  
→ Fraud  
→ Disputes  
→ Cases  
→ Communications

---

# 58. Fraud Operations

Fraud analysts need:

- Fraud queue
- Transaction-risk score
- Device information
- Location
- Merchant
- Previous customer behavior
- Case history

Actions:

- Approve transaction
- Block transaction
- Freeze account
- Replace card
- Contact customer

---

# 59. Dispute Operations

Operations team should manage:

- New disputes
- Investigation
- Merchant evidence
- Temporary credit
- Chargeback
- Resolution

---

# 60. Collections

Add servicing for delinquent accounts.

Stages:

- 1–29 days
- 30–59 days
- 60–89 days
- 90+ days

Functions:

- Contact customer
- Payment arrangement
- Hardship program
- Promise-to-pay
- Escalation

---

# 61. Hardship Assistance

Customers experiencing financial difficulty should be able to request assistance.

Options may include:

- Payment plan
- Temporary reduced payment
- Fee review
- Interest-rate adjustment
- Due-date adjustment

---

# 62. Customer-Service Agent Desktop

Agents need:

- Customer search
- Identity verification
- Account summary
- Transaction history
- Payment history
- Dispute history
- Fraud cases
- Secure messaging
- Notes

---

# 63. Case Management

Create cases for:

- Fraud
- Billing
- Payment
- Rewards
- Complaints
- Card replacement
- Application review

Track:

- Owner
- SLA
- Status
- Priority
- Resolution

---

# 64. Product Administration

Authorized staff should configure:

- APR
- Fees
- Rewards
- Introductory offers
- Eligibility
- Card artwork
- Credit ranges
- Marketing content

Do not hard-code these values in the UI.

---

# 65. Rewards Administration

Manage:

- Reward categories
- Multipliers
- Merchant offers
- Redemption rates
- Expiration
- Promotional campaigns

---

# 66. Offer Management

Marketing teams should configure:

- Welcome offers
- Balance-transfer offers
- Cash-back offers
- Retention offers
- Upgrade offers

Support:

- Effective dates
- Eligibility
- Customer segments

---

# 67. Communication Management

Provide reusable templates for:

- Approval
- Decline
- Payment reminder
- Fraud notification
- Card shipment
- Dispute update
- Reward promotion

---

# 68. Audit Trail

Every sensitive action should log:

- User
- Action
- Timestamp
- Account
- Previous value
- New value
- IP/device
- Reason

---

# 69. Role-Based Access Control

Example admin roles:

- Customer-service representative
- Fraud analyst
- Underwriter
- Collections agent
- Dispute analyst
- Product manager
- Marketing manager
- Operations manager
- System administrator
- Auditor

---

# 70. Compliance Dashboard

Support operational monitoring for requirements such as:

- PCI DSS
- GLBA
- FCRA
- ECOA
- Regulation Z
- Regulation E where applicable
- AML/KYC-related controls where applicable
- Privacy requirements

---

# 71. Reporting

Reports should include:

- Application funnel
- Approval rate
- Portfolio balance
- Credit utilization
- Delinquency
- Charge-offs
- Rewards cost
- Fraud losses
- Dispute volume
- Customer acquisition

---

# 72. Executive Dashboard

Provide high-level KPIs such as:

**Total accounts**

**New accounts**

**Total receivables**

**Average spend**

**Interchange revenue**

**Interest income**

**Rewards expense**

**Fraud losses**

**Charge-offs**

---

# Additional High-Value Features I Recommend for Xenhey

The following features would make the prototype noticeably stronger for demos and sales conversations.

## 73. End-to-End Customer Timeline

Create one timeline showing:

**Product Viewed**

→ **Prequalified**

→ **Application Started**

→ **Application Submitted**

→ **Approved**

→ **Card Issued**

→ **Card Activated**

→ **First Purchase**

→ **First Payment**

→ **Rewards Redemption**

This would be particularly valuable for demonstrating a full customer journey.

---

# 74. What-If Product Simulator

Allow sales or product teams to dynamically change:

- APR
- Annual fee
- Welcome bonus
- Rewards rate
- Minimum credit line

and immediately preview the customer experience.

This aligns especially well with a feature-driven prototype platform.

---

# 75. Customer Journey Replay

Allow demo users to select personas such as:

**Sarah — Travel Rewards Customer**

**Michael — Credit Builder**

**James — Balance Transfer Customer**

**Anna — Premium Cardholder**

Then preload realistic synthetic:

- Transactions
- Statements
- Rewards
- Payments
- Offers
- Notifications

This makes the prototype much more compelling than empty wireframes.

---

# 76. Card Upgrade / Downgrade

Allow eligible customers to move between products.

Example:

**Cash Back Card → Premium Travel Card**

Show:

- New annual fee
- New APR
- New benefits
- Rewards conversion
- Effective date

---

# 77. Retention Offers

When a customer attempts to close an account, offer configurable retention options.

Examples:

- Annual-fee waiver
- Bonus points
- Promotional APR
- Product conversion

---

# 78. Personalized Offers

Use account behavior to display offers such as:

**You frequently spend on travel — earn 3X travel points with Product X.**

or

**You may be eligible for a higher reward tier.**

---

# 79. Financial Health Dashboard

Combine:

- Credit utilization
- Payment consistency
- Interest paid
- Monthly spending
- Recurring expenses
- Credit score
- Debt payoff progress

This converts the card application from a simple servicing portal into a personal-finance experience.

---

# 80. Open Banking / External Account Integration

Allow customers to connect external accounts to:

- Fund payments
- Understand cash flow
- Improve financial insights
- Validate income where appropriate

---

# 81. Event-Driven Notifications

From an architecture perspective, I would model major actions as events:

`ApplicationSubmitted`

`ApplicationApproved`

`CardIssued`

`CardActivated`

`TransactionAuthorized`

`TransactionDeclined`

`StatementGenerated`

`PaymentReceived`

`FraudDetected`

`DisputeOpened`

`RewardsEarned`

`CreditLimitChanged`

This gives you a clean foundation for APIs, messaging, notifications, analytics, and workflow automation.

---

## Recommended Xenhey navigation structure

A strong final navigation would look like this:

```text
Personal Credit Cards

CUSTOMER
├── Dashboard
├── Explore Cards
├── Compare Cards
├── Prequalify
├── Application
├── Application Status
│
├── My Card
│   ├── Card Details
│   ├── Card Controls
│   ├── Digital Card
│   ├── Digital Wallet
│   └── Replace Card
│
├── Transactions
│   ├── Recent Transactions
│   ├── Spending Analytics
│   └── Recurring Payments
│
├── Payments
│   ├── Make Payment
│   ├── Autopay
│   └── Payment History
│
├── Statements
│
├── Rewards
│   ├── Rewards Dashboard
│   ├── Redeem Rewards
│   └── Offers
│
├── Credit
│   ├── Credit Score
│   ├── Credit Utilization
│   ├── Limit Increase
│   └── Payoff Planner
│
├── Fraud & Disputes
│   ├── Fraud Center
│   ├── Report Transaction
│   └── Dispute Tracker
│
├── Profile
├── Alerts
├── Security
└── Support


ISSUER OPERATIONS
├── Admin Dashboard
├── Customer 360
├── Applications
├── Underwriting
├── Accounts
├── Transactions
├── Payments
├── Fraud
├── Disputes
├── Collections
├── Cases
├── Products
├── Rewards
├── Offers
├── Communications
├── Reporting
├── Compliance
├── Audit
└── Administration
```

The current Xenhey structure already separates **Customer Flow**, **Issuer Operations**, and the **Financial Product Catalog**, so this expanded navigation fits naturally into the existing model rather than requiring a complete redesign. :chatgpt-content-reference{index="3"}

### Recommended implementation priority

For the strongest demo, I would build the next iteration in roughly this sequence:

**Phase 1:** Product Catalog → Compare Cards → Application → Approval → Customer Dashboard → Transactions → Payments.

**Phase 2:** Rewards → Card Controls → Fraud → Disputes → Statements → Alerts → Credit Score.

**Phase 3:** Customer 360 → Underwriting Workbench → Fraud Operations → Collections → Product Administration → Analytics.

**Phase 4:** AI assistant → personalized offers → journey replay → financial health → event-driven automation.

That would turn the current **Personal Credit Cards prototype** into a much more complete **customer acquisition + card servicing + issuer operations platform**, suitable for demonstrating a modern bank or fintech credit-card experience.
