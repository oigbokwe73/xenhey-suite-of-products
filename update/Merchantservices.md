The Xenhey Merchant Services prototype establishes three primary areas: **Merchant Flow, Admin Flow, and Financial Product Catalog**. It also explicitly calls out provider approval, pricing, reserves, funding, equipment, network access, PCI scope, and activation as operational considerations. :chatgpt-content-reference{index="0"}

The detailed 65-step model below expands that prototype into a **production-grade Merchant Services platform**. Some capabilities are therefore recommended implementation features rather than claims that every one already exists in the prototype.

---

# 1. Merchant Dashboard

The Merchant Dashboard should be the central workspace for the business owner, finance team, or merchant administrator.

### Primary purpose
Give the merchant an immediate view of payment-processing health without requiring them to search multiple modules.

### Dashboard information
Display:

- Today's sales
- Yesterday's sales
- Month-to-date sales
- Number of transactions
- Average ticket amount
- Approval rate
- Decline rate
- Refund volume
- Chargeback volume
- Pending settlements
- Pending funding
- Latest deposit
- Next expected deposit
- Open disputes
- Compliance status
- Terminal status

### Example

```text
Today's Sales              $46,250
Transactions                   417
Average Ticket              $110.91
Approved                      96.8%
Declined                       3.2%
Pending Settlement         $31,500
Next Funding              Sep 28
Open Chargebacks                 3
PCI Status                 Compliant
```

### Quick actions

Provide buttons for:

- Take Payment
- Issue Refund
- Search Transaction
- Create Payment Link
- Create Invoice
- View Deposit
- Respond to Chargeback
- Download Statement

### User experience

A merchant should be able to answer:

> "How much did I process, what will be deposited, and is anything requiring my attention?"

within a few seconds.

---

# 2. Merchant Onboarding

Merchant onboarding begins the relationship between the payment provider and the business.

### Purpose

Collect sufficient information to:

- Identify the business
- Identify its owners
- Understand expected processing behavior
- Verify risk
- Establish settlement banking
- Determine pricing
- Determine equipment requirements
- Meet regulatory requirements

### Sections

A wizard could use:

```text
1. Business Information
2. Ownership
3. Processing Profile
4. Banking
5. Locations
6. Equipment
7. Documents
8. Agreements
9. Review
10. Submit
```

### Important functionality

Support:

- Save and continue later
- Completion percentage
- Required-field indicators
- Validation
- Conditional questions
- Document upload
- Electronic signature

---

# 3. Merchant Application

The application converts onboarding data into a formal request for merchant-processing services.

### Application states

```text
Draft
   ↓
Submitted
   ↓
Initial Review
   ↓
Underwriting
   ↓
Approved
   ↓
Provisioning
   ↓
Activated
```

Alternative states:

```text
Additional Information Required
Declined
Withdrawn
Expired
Suspended
```

### Application record

Store:

- Application ID
- Merchant
- Submission date
- Product
- Requested processing volume
- Requested equipment
- Pricing program
- Assigned underwriter
- Current status
- Risk classification

### Auditability

Every status change should record:

```text
Previous status
New status
Changed by
Date/time
Reason
Comments
```

---

# 4. KYB / KYC

Merchant Services generally requires both business and ownership verification.

### KYB — Know Your Business

Verify:

- Legal business name
- EIN
- State registration
- Business address
- Industry
- MCC
- Website
- Formation date
- Business status

### KYC — Know Your Customer

For owners or controlling persons:

- Full name
- DOB
- Address
- Identity verification
- Ownership percentage
- Authorized signer status

### Screening

Potential checks include:

- OFAC
- Sanctions
- Adverse business information
- Fraud indicators
- Business-registration validation

### Exception handling

Example:

```text
Business address mismatch
        ↓
Request proof of address
        ↓
Merchant uploads document
        ↓
Analyst reviews
        ↓
Verified
```

---

# 5. Document Management

A dedicated document center prevents sensitive merchant documentation from becoming scattered across email.

### Document categories

Business:

- Articles of incorporation
- Business license
- EIN documentation
- Operating agreement

Owner:

- Driver's license
- Passport
- Identity documents

Banking:

- Voided check
- Bank statement

Financial:

- Processing statements
- Financial statements
- Tax documents

Compliance:

- PCI attestation
- Security documentation

### Document metadata

Maintain:

```text
Document ID
Merchant
Document type
Uploaded by
Upload date
Expiration date
Status
Reviewer
Review comments
Version
```

### Status

```text
Requested
Received
Under Review
Accepted
Rejected
Expired
```

---

# 6. Bank Account Setup

The merchant must provide an account where settlement funds will be deposited.

### Information

Capture:

- Bank name
- Routing number
- Account number
- Account type
- Account holder
- Account purpose

### Verification methods

Possible methods include:

- Micro-deposits
- Bank-data provider
- Manual bank letter
- Voided check
- Account validation API

### Security

After entry:

```text
Routing: *****021
Account: ******4832
```

Do not repeatedly display complete banking information.

### Change workflow

A bank change should be controlled:

```text
Merchant Request
     ↓
MFA Verification
     ↓
Document Validation
     ↓
Operations Approval
     ↓
Bank Validation
     ↓
Effective Date
```

---

# 7. Underwriting

Underwriting determines whether and under what conditions the provider will support the merchant.

### Underwriter workspace

Show:

- Business profile
- Owners
- Processing history
- Expected sales
- Average ticket
- Maximum ticket
- Chargeback history
- Refund history
- Bank verification
- Industry risk
- Documents
- External checks

### Decisions

An underwriter could:

- Approve
- Approve conditionally
- Request more information
- Escalate
- Decline

### Conditional approval

For example:

```text
Approved subject to:

$100,000 monthly processing limit
$5,000 maximum transaction
10% rolling reserve
T+2 funding
```

---

# 8. Merchant Risk Scoring

Risk scoring creates a structured way to assess merchants.

### Risk dimensions

Evaluate:

- Industry
- Geography
- Business age
- Processing volume
- Average ticket
- Maximum ticket
- Card-not-present percentage
- Refund rate
- Chargeback rate
- Financial strength
- Ownership characteristics

### Example model

```text
Industry Risk          15
Processing Risk        10
Financial Risk          5
Fraud Risk             10
Chargeback Risk         5
--------------------------
Total                  45
```

The score should support—not automatically substitute for—appropriate underwriting and compliance review.

---

# 9. Merchant Pricing

Merchant pricing controls what the merchant pays for processing.

### Pricing models

Support:

- Interchange plus
- Flat rate
- Tiered pricing
- Subscription pricing
- Blended pricing

### Example

```text
Interchange
+
0.30%
+
$0.10 per transaction
```

### Fee types

Support:

- Authorization fee
- Transaction fee
- Monthly fee
- Statement fee
- PCI fee
- Gateway fee
- ACH fee
- Chargeback fee
- Terminal fee
- Early termination fee

### Pricing history

Never simply overwrite pricing.

Maintain:

```text
Version
Effective date
Expiration date
Approved by
Reason
```

---

# 10. Reserve Management

Some merchants may require funds to be held to protect against future liabilities.

### Reserve types

Support:

- Fixed reserve
- Rolling reserve
- Percentage reserve
- Transaction reserve

### Example

Merchant processes:

```text
$100,000
```

Reserve:

```text
10%
```

Funding:

```text
$90,000 minus other fees
```

Reserve held:

```text
$10,000
```

### Reserve ledger

Track:

- Amount withheld
- Date withheld
- Release eligibility
- Release date
- Reason
- Balance

---

# 11. Merchant Account Activation

Approval alone does not mean the merchant can process payments.

Activation coordinates all downstream setup.

### Activation checklist

Example:

```text
✓ Merchant approved
✓ Bank verified
✓ Pricing configured
✓ Merchant ID generated
✓ Gateway configured
✓ Terminal configured
✓ Funding configured
✓ PCI enrollment completed
✓ Credentials issued
✓ Test transaction passed
```

### Activation status

```text
Approved
Provisioning
Configuration
Testing
Ready
Active
```

---

# 12. Merchant Locations

Multi-location merchants need location-level configuration.

### Hierarchy

```text
Acme Restaurants
│
├── Corporate
├── Atlanta Store
├── Charlotte Store
├── Miami Store
└── Tampa Store
```

### Each location may have

- Address
- Store number
- Merchant ID
- Terminal IDs
- Bank account
- Manager
- Time zone
- Funding configuration
- Sales reporting
- Processing limits

### Reporting

Allow users to view:

```text
All locations
Region
Single location
Single terminal
```

---

# 13. Payment Acceptance

This is the core processing capability.

### Payment channels

Support:

- POS
- Ecommerce
- Mobile
- Virtual terminal
- Payment link
- Recurring billing
- Invoice payment

### Payment methods

Potentially:

- Credit card
- Debit card
- ACH
- Contactless
- Apple Pay
- Google Pay
- Network tokens

### Typical flow

```text
Customer
   ↓
Merchant
   ↓
Gateway
   ↓
Processor
   ↓
Card Network
   ↓
Issuer
   ↓
Approved / Declined
```

---

# 14. Transaction Management

All payments should create a searchable transaction record.

### Record fields

Store:

- Transaction ID
- Merchant ID
- Location
- Terminal
- Date
- Time
- Amount
- Currency
- Payment method
- Card brand
- Masked card number
- Authorization
- Status
- Settlement status

### Statuses

```text
Pending
Authorized
Captured
Approved
Declined
Voided
Refunded
Settled
Disputed
```

---

# 15. Transaction Search

Payment operations depend heavily on search.

### Search criteria

Allow combinations of:

- Transaction ID
- Date
- Amount
- Customer
- Last four digits
- Authorization code
- Merchant
- Location
- Terminal
- Card brand
- Status

### Example

An employee receives a call:

> "I paid $247.98 yesterday using my Visa ending in 9321."

The user should be able to locate the payment quickly using those fields.

---

# 16. Refunds

Refund functionality returns previously collected money.

### Types

- Full refund
- Partial refund

### Example

Original payment:

```text
$500
```

Partial refund:

```text
$125
```

Remaining captured amount:

```text
$375
```

### Controls

Require:

- Refund permissions
- Original transaction
- Amount validation
- Reason
- Confirmation

High-value refunds may require manager approval.

---

# 17. Voids

A void typically cancels a transaction before settlement.

### Difference

```text
Before settlement → Void
After settlement  → Refund
```

### Workflow

```text
Locate transaction
     ↓
Verify eligibility
     ↓
Select Void
     ↓
Provide reason
     ↓
Confirm
     ↓
Processor notified
```

---

# 18. Virtual Terminal

A Virtual Terminal lets authorized employees manually enter payments through a web interface.

### Use cases

- Phone order
- Mail order
- Customer-service payment
- Internal billing

### Fields

- Amount
- Customer
- Card
- Expiration
- CVV
- Billing ZIP
- Invoice
- Description

### Security

Use:

- Tokenization
- PCI controls
- MFA
- Restricted RBAC
- Audit trails

---

# 19. Payment Links

A payment link lets merchants collect money without building ecommerce checkout.

### Workflow

```text
Merchant creates request
        ↓
System generates secure link
        ↓
Customer receives link
        ↓
Customer enters payment
        ↓
Payment processed
        ↓
Merchant notified
```

### Configuration

Include:

- Amount
- Customer
- Description
- Invoice
- Expiration
- Allowed payment methods

---

# 20. Recurring Payments

Recurring billing supports memberships, subscriptions, and repeat billing.

### Configuration

Store:

- Customer
- Payment token
- Amount
- Frequency
- Start date
- End date
- Retry policy

### Frequencies

- Weekly
- Monthly
- Quarterly
- Annual
- Custom

### Failed payments

Workflow:

```text
Payment Failed
     ↓
Retry
     ↓
Notify Customer
     ↓
Retry Again
     ↓
Suspend Subscription
```

---

# 21. Customer Management

Merchants should be able to maintain customer profiles.

### Customer record

Include:

- Customer ID
- Name
- Company
- Email
- Phone
- Addresses
- Payment tokens
- Transaction history
- Invoices
- Subscriptions

Never store unprotected raw payment credentials as ordinary customer data.

---

# 22. Invoice Management

Invoices connect accounts receivable to Merchant Services.

### Invoice structure

```text
Invoice #INV-23091

Customer: ABC Company

Consulting       $2,500
Support             $500
Tax                  $90
-------------------------
Total              $3,090
```

### Status

- Draft
- Sent
- Viewed
- Partial
- Paid
- Overdue
- Cancelled

### Actions

- Email
- Download
- Pay
- Send reminder
- Void
- Refund

---

# 23. Settlement Management

Settlement represents processor-level grouping and completion of transactions.

### Settlement details

Show:

- Batch number
- Processing date
- Gross sales
- Refunds
- Fees
- Adjustments
- Chargebacks
- Reserve
- Net amount

### Example

```text
Gross Sales        $50,000
Refunds             -1,000
Fees                  -900
Chargebacks            -250
Reserve              -1,000
---------------------------
Net Settlement      $46,850
```

---

# 24. Funding Management

Funding represents actual money being transferred to the merchant.

Settlement and funding should be treated separately.

### Funding record

Include:

- Funding ID
- Settlement IDs
- Amount
- Bank account
- Expected date
- Actual date
- Status

### Status

```text
Scheduled
Pending
Sent
Completed
Failed
Held
Returned
```

---

# 25. Deposit Reconciliation

Accounting teams need to explain how sales resulted in a particular deposit.

### Example

```text
Gross Processing           $125,000
Refunds                      -3,000
Chargebacks                    -500
Fees                         -2,200
Reserve                      -5,000
Adjustments                    +250
-----------------------------------
Bank Deposit                $114,550
```

The system should allow reconciliation from:

**bank deposit → funding → settlements → transactions**

and in the reverse direction.

---

# 26. Batch Management

Transactions are often grouped into batches.

### Capabilities

- Open batch
- View transactions
- Close manually
- Auto close
- Reopen where supported
- Identify batch exceptions

### Batch fields

- Batch ID
- Terminal
- Location
- Open time
- Close time
- Count
- Gross amount
- Refund amount
- Net amount

---

# 27. Chargebacks

Chargebacks occur when customers dispute card transactions.

### Merchant workflow

```text
Chargeback Received
        ↓
Review Transaction
        ↓
Review Reason Code
        ↓
Collect Evidence
        ↓
Submit Response
        ↓
Processor Review
        ↓
Won / Lost
```

### Important data

- Case number
- Reason code
- Original transaction
- Amount
- Due date
- Status
- Evidence

---

# 28. Dispute Evidence Management

Merchants need structured evidence submission.

### Evidence examples

- Receipt
- Signed agreement
- Invoice
- Shipping confirmation
- Delivery confirmation
- Refund policy
- Customer communication
- Login records

### Checklist

```text
✓ Receipt
✓ Invoice
✓ Delivery confirmation
✗ Customer correspondence
```

The system should identify missing required evidence before submission.

---

# 29. Fraud Monitoring

Fraud controls should evaluate transaction patterns.

### Signals

- Transaction velocity
- Repeated declines
- Unusual amount
- New device
- Suspicious geography
- CVV mismatch
- AVS mismatch
- Repeated card attempts
- Card testing

### Possible actions

```text
Allow
Review
Challenge
Decline
Hold
Block
```

---

# 30. PCI Compliance

PCI-related workflows help merchants understand their compliance responsibilities.

### Merchant center

Display:

- PCI status
- SAQ status
- Scan status
- Due date
- Expiration
- Action items

### Example

```text
PCI Status: Action Required

SAQ                  Complete
Network Scan         Failed
Remediation          Required
Next Review          Oct 31
```

---

# 31. Terminal Management

Terminals should be inventory-controlled assets.

### Device record

Store:

- Device ID
- Serial number
- Model
- Merchant
- Location
- Terminal ID
- Firmware
- Connectivity
- Status

### Status

- Inventory
- Assigned
- Shipped
- Installed
- Active
- Offline
- Returned
- Retired

---

# 32. Equipment Ordering

Merchants may require physical devices.

### Products

Examples:

- Countertop terminal
- Wireless terminal
- PIN pad
- Mobile reader
- Printer
- Scanner

### Workflow

```text
Requested
   ↓
Approved
   ↓
Ordered
   ↓
Shipped
   ↓
Delivered
   ↓
Installed
   ↓
Activated
```

Track shipment information and serial numbers.

---

# 33. Terminal Configuration

Devices need configuration before production use.

### Settings

Configure:

- Merchant ID
- Terminal ID
- Currency
- Time zone
- Receipt options
- Tipping
- Contactless
- Debit
- Network settings
- Batch close
- Processor endpoint

Configuration changes should be audited.

---

# 34. Network Connectivity

Payment devices depend on reliable connectivity.

### Supported connectivity

Potentially:

- Ethernet
- Wi-Fi
- Cellular
- Private network
- Internet gateway

### Monitoring

Track:

```text
Terminal online/offline
Gateway reachable
Processor reachable
Latency
Last heartbeat
```

### Alert

Example:

```text
Terminal ATL-025 has been offline for 12 minutes.
```

---

# 35. Reporting

Reporting turns transaction information into operational data.

### Reports

Sales:

- Daily
- Weekly
- Monthly
- Location

Transaction:

- Approved
- Declined
- Refunded
- Voided

Financial:

- Funding
- Settlement
- Fees
- Reserve

Risk:

- Chargebacks
- Fraud
- PCI

---

# 36. Analytics

Analytics differs from reporting by helping users understand trends.

### Examples

Show:

- Sales trend
- Approval rate
- Average ticket
- Peak hours
- Sales by channel
- Sales by card brand
- Chargeback percentage
- Refund percentage
- Funding trends

### Example insight

```text
Card-not-present transactions increased 22% month-over-month.
```

---

# 37. Statements

Statements provide an official recurring summary.

### Monthly statement

Include:

- Processing volume
- Transactions
- Refunds
- Interchange
- Processor fees
- Chargeback fees
- Gateway fees
- Equipment charges
- Total fees
- Net funding

Allow:

- View online
- PDF download
- Historical retrieval

---

# 38. Merchant Users

Businesses usually need multiple users.

### Common roles

- Owner
- Administrator
- Manager
- Accountant
- Customer service
- Analyst
- Read only

### User management

Provide:

- Invite user
- Activate
- Disable
- Reset MFA
- Change role
- Review last login

---

# 39. Role-Based Access Control

RBAC should define exactly what each merchant employee can do.

Example:

| Permission | Owner | Manager | Accountant | CSR |
|---|---:|---:|---:|---:|
| View transactions | ✓ | ✓ | ✓ | ✓ |
| Refund | ✓ | ✓ | No | Limited |
| View banking | ✓ | No | ✓ | No |
| Manage users | ✓ | No | No | No |
| Statements | ✓ | ✓ | ✓ | No |

Support least privilege.

---

# 40. Merchant Profile Management

The merchant should be able to maintain its business profile.

### Editable fields

- DBA
- Contact
- Phone
- Email
- Address
- Website

### Controlled fields

Sensitive changes should require review:

- Legal entity
- EIN
- Ownership
- Bank account
- Processing limits

Example:

```text
Bank Account Change
     ↓
Verification
     ↓
Operations Review
     ↓
Approval
```

---

# 41. Notifications

Users should not need to constantly monitor dashboards.

### Events

Notify for:

- Payment failure
- Deposit completed
- Funding hold
- Chargeback
- Chargeback deadline
- PCI expiration
- Terminal offline
- Document request
- Application approval

### Channels

- In-app
- Email
- SMS
- Push
- Webhook

Allow user preferences by event type.

---

# 42. Admin Dashboard

Operations teams need a completely different dashboard than merchants.

### Operational metrics

Show:

- New applications
- Pending underwriting
- Applications aging
- Activation backlog
- Funding exceptions
- Suspended merchants
- Fraud alerts
- Chargebacks
- PCI exceptions
- Device incidents

### Example

```text
Applications Awaiting Review       47
SLA Breaches                        4
Funding Holds                      12
High-Risk Alerts                    8
Open Chargebacks                   93
PCI Exceptions                     31
```

---

# 43. Merchant Administration

Operations personnel need a complete internal view of every merchant.

### Merchant 360

Display:

```text
Profile
Ownership
Banking
Processing
Transactions
Funding
Pricing
Reserve
Risk
Terminals
Documents
Cases
Compliance
Users
Audit history
```

This should function as the authoritative operational merchant record.

---

# 44. Application Administration

Internal staff manage submitted merchant applications.

### Functions

- Assign analyst
- Reassign
- Review
- Add note
- Request document
- Approve
- Decline
- Escalate
- Place on hold

### SLA

Track:

```text
Submitted: Sep 21 10:03 AM
SLA: 48 hours
Age: 31 hours
Status: Underwriting
Owner: Jane Smith
```

---

# 45. Operations Work Queues

Queues organize operational work.

### Possible queues

- New applications
- Underwriting
- Document review
- Merchant activation
- Funding exceptions
- Device provisioning
- Chargebacks
- Fraud
- PCI
- Support

### Queue columns

- Work item
- Merchant
- Priority
- Owner
- Age
- SLA
- Status

Supervisors should be able to redistribute work.

---

# 46. Case Management

Problems that require investigation should become formal cases.

### Case types

- Settlement
- Funding
- Transaction
- Terminal
- Chargeback
- Fraud
- PCI
- Banking
- Merchant profile

### Lifecycle

```text
New
 ↓
Assigned
 ↓
In Progress
 ↓
Waiting on Merchant
 ↓
Resolved
 ↓
Closed
```

Cases should maintain:

- Comments
- Documents
- Timeline
- Tasks
- Ownership
- SLA

---

# 47. Merchant Notes

Operations users often need contextual information that should not appear to merchants.

### Note categories

- Underwriting
- Risk
- Fraud
- Support
- Compliance
- Sales
- Operations

### Example

```text
Internal Note
09/25/2026
Merchant contacted regarding unusual volume increase.
Merchant confirmed seasonal promotion.
```

Support visibility levels such as:

- Internal
- Restricted
- Customer-visible where appropriate

---

# 48. Pricing Administration

Operations must manage pricing rules centrally.

### Functions

- Create rate plans
- Clone plans
- Assign plans
- Override fee
- Schedule change
- Approve exception
- Audit changes

### Example

```text
STANDARD-RETAIL-001

Markup           0.25%
Transaction      $0.10
Monthly Fee      $15
Chargeback Fee   $25
```

---

# 49. Funding Administration

Operations manages exceptions to merchant payouts.

### Functions

- View pending funding
- Place hold
- Release hold
- Change timing
- Investigate failure
- Change destination after verification
- Reissue funding

### Hold reasons

- Fraud investigation
- Bank failure
- Chargeback exposure
- Compliance review
- Account change
- Reserve adjustment

---

# 50. Reserve Administration

Operations needs tools for reserve policies.

### Capabilities

- Establish reserve
- Increase/decrease percentage
- Add manual hold
- Release reserve
- Schedule future release
- Review reserve ledger

### Approval

Large reserve modifications should require dual authorization.

---

# 51. Chargeback Administration

Internal dispute staff need greater functionality than merchants.

### Functions

- Receive processor cases
- Assign analyst
- Monitor deadlines
- Validate evidence
- Communicate with merchant
- Submit representment
- Record result
- Apply financial adjustment

### Dashboard

Track:

- Open
- Due today
- Past due
- Won
- Lost
- Win rate

---

# 52. Fraud Operations

Fraud analysts need a case-based environment.

### Capabilities

- Review alert
- View payment history
- Compare device/IP
- Examine velocity
- Review merchant patterns
- Add watch list
- Suspend processing
- Hold funding
- Escalate

### Decision trail

Record why each action was taken.

---

# 53. Merchant Suspension

Different capabilities may need independent suspension.

### Controls

Suspend:

- Login
- Payment processing
- Refunds
- Funding
- Individual terminal
- Specific payment channel

### Example

A fraud investigation might allow:

```text
Merchant portal: ACTIVE
Processing:      ACTIVE
Funding:         HOLD
Refunds:         ACTIVE
```

rather than disabling everything.

---

# 54. Audit Trail

Audit logging is critical for payments.

### Capture

For every important event:

- Actor
- Role
- Action
- Resource
- Old value
- New value
- Date
- Time
- IP
- Correlation ID

### Example

```text
User: OPS1049
Action: Change Funding Schedule
Old: T+1
New: T+2
Merchant: MID-100493
Reason: Risk Review
```

Audit information should not be editable by ordinary users.

---

# 55. Financial Product Catalog

The Xenhey experience explicitly includes a Financial Product Catalog alongside the merchant and admin flows. :chatgpt-content-reference{index="1"}

The catalog can expose adjacent services.

### Categories

Banking:

- Business checking
- Savings
- Money market

Payments:

- Merchant services
- ACH
- Gateway
- POS

Credit:

- Credit card
- Line of credit
- Business loan

Treasury:

- Wire
- ACH
- Cash management
- Remote deposit

### Catalog item

Each product should contain:

- Description
- Eligibility
- Benefits
- Pricing
- Required information
- Apply button

---

# 56. Cross-Sell Recommendations

Merchant processing creates signals that can support relevant product recommendations.

### Examples

High balances:

```text
Recommend Business Savings
```

High processing growth:

```text
Recommend Working Capital
```

Large international sales:

```text
Recommend Foreign Exchange Services
```

### Important design principle

Recommendations should explain why the product is relevant rather than simply advertising unrelated services.

---

# 57. Integration APIs

APIs enable other systems to use Merchant Services capabilities.

### Example API structure

```http
GET /api/merchants/{merchantId}

GET /api/transactions

POST /api/payments

POST /api/refunds

GET /api/settlements

GET /api/funding

GET /api/disputes

POST /api/disputes/{id}/evidence
```

### API concerns

Implement:

- OAuth
- API authorization
- Rate limiting
- Idempotency
- Correlation IDs
- Pagination
- Versioning
- Error standards

---

# 58. Webhooks

Webhooks push events to external applications.

Without them, consuming systems would constantly poll Merchant Services.

### Example events

```text
payment.approved
payment.declined
payment.refunded

settlement.completed

funding.sent
funding.failed

chargeback.created

merchant.approved
merchant.activated

terminal.offline
```

### Reliability

Support:

- Signed payloads
- Retries
- Dead-letter handling
- Event ID
- Timestamp
- Delivery history

---

# 59. Accounting Integration

Merchant financial activity should be exportable into accounting platforms.

### Integration examples

- QuickBooks
- Xero
- NetSuite
- Dynamics 365 Finance
- SAP

### Data

Synchronize:

- Sales
- Deposits
- Fees
- Refunds
- Chargebacks
- Adjustments

### Example

```text
Merchant Settlement
       ↓
Accounting Connector
       ↓
General Ledger
```

Provide reconciliation IDs so finance teams can trace transactions.

---

# 60. CRM / Customer Support Integration

Merchant Services should integrate with systems managing merchant relationships.

### CRM use

- Leads
- Merchant applications
- Account ownership
- Sales opportunities
- Cross-selling

### ITSM use

ServiceNow or equivalent may manage:

- Terminal incident
- Funding issue
- Merchant support case
- Access request
- Change request

### Integration

```text
Merchant Services
       ↓
Event/API
       ↓
ServiceNow Case
       ↓
Case ID returned
       ↓
Merchant Services displays status
```

---

# 61. Security

Security should span the entire solution rather than being a standalone screen.

### Identity

Use:

- OIDC
- OAuth 2.0
- MFA
- SSO
- Conditional Access where appropriate

### Authorization

Use:

- RBAC
- Least privilege
- Merchant isolation
- Admin separation of duties

### Data protection

Use:

- TLS
- Encryption at rest
- Tokenization
- Key management
- Secrets management

### Operational controls

Include:

- Audit logging
- Threat detection
- Security monitoring
- Session controls
- Login alerts

---

# 62. Compliance & Regulatory Management

This should be a dedicated platform capability.

### Areas

Depending on the business model and jurisdiction:

- PCI DSS
- KYC
- KYB
- AML controls
- OFAC screening
- Data retention
- Privacy
- Recordkeeping

### Compliance profile

For each merchant maintain:

```text
Requirement
Status
Evidence
Effective date
Expiration
Owner
Exception
```

### Dashboard

Show:

```text
Compliant
Expiring Soon
Action Required
Past Due
Exempt
```

---

# 63. Monitoring & Observability

A payment platform requires end-to-end operational monitoring.

### Monitor

Applications:

- API latency
- Errors
- exceptions

Payments:

- Authorization latency
- Approval rate
- Processor failures

Infrastructure:

- CPU
- memory
- network
- queue depth

Business:

- Transaction volume
- funding failures
- settlement failures

### Correlation

Every payment should have a correlation ID:

```text
Web
 ↓
API
 ↓
Payment Service
 ↓
Gateway
 ↓
Processor
```

The same identifier should make the complete path traceable.

---

# 64. Workflow & Business Rules Engine

Many Merchant Services processes should be configurable rather than hard-coded.

### Rule example

```text
IF
monthlyVolume > $500,000

AND
cardNotPresent > 70%

THEN
require Senior Underwriter Review
```

Another:

```text
IF
chargebackRate > threshold

THEN
create Risk Review Case
AND
notify Risk Team
```

### Workflow applications

Use this engine for:

- Applications
- Underwriting
- Pricing approvals
- Refund approvals
- Fraud reviews
- Funding holds
- Chargebacks
- Compliance
- Account changes

This makes the platform easier to change as policies evolve.

---

# 65. Platform Administration & Configuration

The final capability provides configuration of the entire Merchant Services ecosystem.

### Administrative configuration

Manage:

**Products**

```text
Merchant Services
ACH
POS
Gateway
Virtual Terminal
```

**Fees**

```text
Transaction fees
Monthly fees
Gateway fees
Chargeback fees
```

**Reference data**

```text
MCC codes
Industries
Countries
Currencies
Card brands
Reason codes
```

**Rules**

```text
Risk thresholds
Approval thresholds
Transaction limits
Refund limits
Reserve thresholds
```

**Security**

```text
Roles
Permissions
Authentication policies
Session policies
```

### Feature flags

Allow features to be enabled gradually:

```text
Payment Links      ON
ACH                ON
Virtual Terminal   ON
Recurring Billing  OFF
Same-Day Funding   Pilot
```

This is especially valuable for a SaaS platform serving multiple financial institutions or payment providers.

---

# How the 65 capabilities work together

The complete lifecycle is easier to understand as one continuous journey:

```text
                    MERCHANT ACQUISITION
                           │
                           ▼
                 1–6 Onboarding / KYB
                           │
                           ▼
                  7–10 Underwriting
                           │
                           ▼
                 11–12 Provisioning
                           │
                           ▼
        ┌──────────────────┴──────────────────┐
        │                                     │
        ▼                                     ▼
 13–22 PAYMENTS                        31–34 EQUIPMENT
        │
        ▼
 23–26 SETTLEMENT
        │
        ▼
      FUNDING
        │
        ▼
     BANK ACCOUNT
```

While payments are running:

```text
Payments
   │
   ├──► 27–28 Chargebacks
   │
   ├──► 29 Fraud
   │
   ├──► 30 PCI
   │
   ├──► 35–37 Reporting
   │
   └──► 41 Notifications
```

Operations supports everything through:

```text
42 Admin Dashboard
      │
      ├── 43 Merchant Administration
      ├── 44 Application Administration
      ├── 45 Work Queues
      ├── 46 Cases
      ├── 47 Notes
      ├── 48 Pricing
      ├── 49 Funding
      ├── 50 Reserves
      ├── 51 Chargebacks
      ├── 52 Fraud
      ├── 53 Suspensions
      └── 54 Audit
```

And the surrounding platform capabilities are:

```text
55 Financial Product Catalog
56 Cross-Sell
57 APIs
58 Webhooks
59 Accounting
60 CRM / ITSM
61 Security
62 Compliance
63 Monitoring
64 Workflow / Rules
65 Platform Administration
```

## Recommended application navigation

For the **Merchant Portal**:

```text
Dashboard
Payments
Transactions
Customers
Invoices
Settlements
Funding
Disputes
Equipment
Reports
Statements
Compliance
Products
Account
```

For the **Merchant Services Operations Portal**:

```text
Operations Dashboard
Applications
Underwriting
Merchants
Risk
Fraud
Transactions
Funding
Reserves
Chargebacks
Equipment
Compliance
Cases
Reports
Administration
```

For implementation, I would treat these **65 capabilities as the Level-1 functional requirements**. Underneath them, the solution would expand into several hundred user stories—for example, **Merchant → Transactions → Search Transaction → View Transaction → Refund Transaction → Approval → Processor → Audit → Notification**—which gives you the level of detail needed to build the complete Xenhey Merchant Services customer and admin experience.
