## Merchant Services UI examples

![Image](https://images.openai.com/static-rsc-4/pinRi8U91HBqnaIoA0moAPz5y8iaykUvZGl-LhSExMU8LKV9ANitySc8QgpxmsoEtDtScueYqI_s-MoBs3dCtipINZ39x-Uoe1u3oCrzok8QgqtY3mTKeL4jmwKTxDMPwW9qXvqbN3mKTfphaxiFbtH9R1UC2-cwH6MGkJQd0Jabd7nKGrveQF-1u7tTxUKV?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/WVVw0QVR9o81cq4Yqnpr5pP4C82dwJe7ZjW9stJeNnoXrhu6phg34TEQrNHQt2A7bYFyMy2eH6ZYfXpW2MNmKcOo7Rt7JNqawYvf-YYBegvLalwYyZQUC8tAgoVCUGPuiXGHSSgvrTXukS179MN8IYPgs5kYynFrXmwOzOJti--zV-jMxIPjTeu4YoaqC8JF?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/-o96XUXQdhbCoxppi7NwC3GFEtCDLBdEeF43mGR7S0mXsjOp1NJRDXCtzW3s108C4Yro3MBDzZrAInMnj_7yPC5QBSYBSP4niw9fDqOgzmQUgKd_RNLPRM1QKx7FvAABm59ZVpW4i1JKV9BLTPf7ROTYUAQX-5hIR2g3zYX8_0P1-YOXwQNE2kQpEReivFVP?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/ahQSUbr1Jvh7dQMtaskIq31yUZqJFnnEkJlNNq1uRD5l2yrdio_VEHEDcQwgrv3Ufz-70__ItJ4Kby2ql4lnK92IJZwZwyqJTr5iU_-1Go0bgvDUUTAadtaAxHlYh3QjOk4KV4pkAqjzM_1t24hooLkEuDoYimxkh2kdvs97KgtW7hBtPHUXfzFtR8Q8Nj6Q?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/gnos2c4dmFt9u0zHGqpdq1nwVBy4oJiKQxNBIvKZAENuJKgzkBlttEpoyYl3xe-nTvWBILH88ugtRtsIYPXUIP6hQ63osJLrT1c-E3k-AKwVyuTGvwbF5fXY7a5FiB2kIqLXCOjmUJ9Sen5-69thiq_lFIP0qNjR5d_q13SotoPuAGwdDDzY9DcpHjfrHZZ9?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/g8hSvQ3NBptn-0qcQa2DdG-QjAnrBUz-hYM1qCb6EV8rz7Y9VuB-YQDzad8PSTn3BQPEbAXnn6eezYprli-OA_WwgWb9Wzd2HScOAa_so5es_F87ZdjbsyXL2YehVTtiHyWVzOtavmAuWlkVE8WOYLLutQvvbXpCs0pzgJOqJrM6QQbG4xOJ-Q6xDGDrbA6G?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/2TulnsEphjpPjk_7o-PUt1AZJZfZ25t0hs-CPsWi9thATEuw5uQQbwMz-PH3YFJSdU5r-W6S4Fuj_N8ed3RaM76jBT0gcQ4n5aFGAzUObjehBAzeqFzhQ7qJoc7fWL0rzmrw4PMLylfhr8Kg041og5msk651gllGAaTqz_QIil5XVxGQUJpA5HWxLRS8PFAT?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Rv5cdx6rxbvjlyQEvoljJ-zyxl5JPV9BYeQdOzKeRpID2SgXB8gibe9h9BpIR_YNq_LsyR354DkvcnhtrtjCLxgF4KZR77BSITp5BVXqYPztHvVKWyBuvfBDmUglA1Bq4xWgVQmbHFDsUgU75G3e6k4x_TWTuwKsQ3DHHOiMyOz0H487GVs2k2qtodCOMzjL?purpose=fullsize)

### 1. Merchant dashboard

A customer-facing landing page similar to your current [Xenhey Merchant Services dashboard](https://www.xenhey.com/api/store/57CC7857B9F24BF2A121D6C192E07BD9).

Include:

* Application status and progress
* Monthly processing volume
* Deposits awaiting settlement
* Open information requests
* Chargebacks and refunds
* PCI compliance status
* Recent activity
* “Continue application” action

### 2. Merchant onboarding wizard

Use a multi-step intake form:

1. Business information
2. Ownership and control
3. Products and services
4. Processing volume
5. Sales channels
6. Fraud and chargeback controls
7. PCI readiness
8. Settlement account
9. Equipment and integration
10. Agreements and submission

Each step should show completion status, validation errors, Save Draft, Previous and Continue buttons.

### 3. Application records table

| Application | Merchant        | Channel      | Status              | Monthly volume | Updated | Action   |
| ----------- | --------------- | ------------ | ------------------- | -------------: | ------- | -------- |
| MS-10421    | Metro Café LLC  | Card present | Risk review         |      $25K–$50K | Sep 11  | Edit     |
| MS-10422    | Horizon Retail  | E-commerce   | Draft               |     $50K–$100K | Sep 10  | Continue |
| MS-10423    | Greenway Dental | Recurring    | Documents requested |      $10K–$25K | Sep 9   | Upload   |

Recommended controls:

* Keyword search
* Status and channel filters
* Date range
* Sortable columns
* Edit/Continue action
* CSV export
* Pagination
* Create Application button

### 4. Processing profile

Provide cards and charts for:

* Monthly card volume
* Average and maximum ticket
* Card-present percentage
* E-commerce percentage
* Recurring payments
* International payments
* Refund and chargeback rates
* Seasonal volume patterns

### 5. Pricing and settlement

Display:

* Interchange-plus or flat-rate pricing
* Transaction fees
* Monthly platform fees
* Chargeback fees
* Equipment costs
* Reserve requirements
* Expected funding schedule
* Settlement-account verification
* Pricing acknowledgment

### 6. Equipment and integration

Use selectable product cards for:

* Countertop terminal
* Wireless terminal
* Mobile reader
* Smart POS
* Virtual terminal
* Hosted checkout
* E-commerce plug-in
* Custom API integration

Each card should show availability, price, compatibility and setup status.

### 7. Application-status tracker

```mermaid
flowchart TD
    A["Intake"] --> B["Documents"]
    B --> C["Business verification"]
    C --> D["Risk and pricing review"]
    D --> E["Provider decision"]
    E --> F["Activation"]
```

Show completed, active, blocked and upcoming stages with dates and outstanding tasks.

### 8. Admin application pipeline

Operations users need:

* Applications by stage
* Assigned reviewer
* Days in current stage
* Risk level
* Missing documents
* SLA warning
* Provider submission status
* Approval or decline decision
* Bulk assignment and export

### 9. Underwriting workspace

Use a three-column layout:

* Left: merchant profile and navigation
* Center: selected review form
* Right: risk alerts, missing information and reviewer notes

Recommended actions:

* Approve
* Conditionally approve
* Request information
* Place on hold
* Escalate
* Decline

### 10. Merchant monitoring dashboard

After activation, display:

* Transaction volume
* Approval rate
* Refund rate
* Chargeback ratio
* ACH return rate
* Fraud alerts
* Settlement exceptions
* PCI expiration
* Volume variance
* Merchant risk tier

A strong overall design direction would combine a Stripe-style clean dashboard, a Square-style guided merchant experience, and an Adyen-style operational review workspace.
