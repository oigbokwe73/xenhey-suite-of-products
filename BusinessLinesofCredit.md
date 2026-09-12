Your [Xenhey Business Lines of Credit page](https://www.xenhey.com/api/store/928D48344AF64AF68F28113A10AE3346) opens a **Customer Dashboard**, but currently emphasizes applications rather than managing an active credit line. The main opportunity is to make **available credit, draw requests, repayments and reporting obligations** the primary experience after activation.

I reviewed its HTML and JavaScript. I did not submit applications, request funds or test separately linked pages and backend integrations.

**Business Lines of Credit UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/9ElL5DiAXvBu3HEk-aQu1vAtYjTgNxgOFWssrGer-UWA6P4ADhXoeeAK1hsk2s-NzXTRCs1vite4gQ1aULsXD_CqBiKqFtBPgQGHopuBkONpdalQGHriZCJHnemsbLJgV_wqrunHEcGPSMjWWaCp-sWEwoPwuYJug3LC3HZBdCqMFO0D260UAV9iYrMcOz1I?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/hizKSeVDbSqHDXOnS2pbAJxXqyZyRbO-CLchUZeMxmrjqfod1PuZJcCqCEpvyAkwBFglxTSfuBNPSWokTKRd1EjS4YpIe4eS4zYLD4uK8AziEaFq9NryoGmSHeGL-PG_849ZF6wElbBnyId_-jQx8qCS-XQeye6z8wABR7Ebcudapqct9VsceScl1XjAVJev?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/cFjmXxVxBItjL6vGUiqmpnLw9fm-Eoc3oQVeIsGDG_ZTalBtNfNmPd37r2liQtIyLFcFkabkMMuvZHfZQKzbVOXMKpYRPjpdm7eTxEbIR5cwn_W7GJ8Lvm_3iAMaOyBlL9kInPAD-dd7VZZgHhSQZZRRejDhXKx--XX4LHyBDlSxot-97F6mJAoTj7oRMbL3?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/izBVget9JvWqYLKYv6_yialVK2s5DgiIF-TFkgSgDKfZhihbrxWxnB4vvfZj2qLnIBr4EUmB4pbPlO3Bm4HAlGv7Z4LkwI7T-wbr12cLtOxFORDpnHF115Y-c-Uip_XQDcMNADoVOxaXLB56EcBTEgpnJltF5MYMy-zFFGkE-4KaBkEpk5E4c_P4ZY6JjMdR?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Kp_8Q_B8hYrWnypHVk2mfkaGzruV5SzN9ZhhFMC0iBTTbLUQKdv6lwFyGEX4Wz__dsWcJTcb_ODju_nHp3Kl0Nhxp5h4BYzc0ecNn6Y7spV07XURqeAWlNUz100cNE-6PIrjfE068v525gUATMx587XPqqP5i3A--xNzd5l98PyDzBLr0kZQKNPEqeqzAuH3?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/WPJn1WliopkaRBR4L5KO5I22v3P2C5DIEkACfT22dXBMn3WnZDy-FpGfTLPmfCefoRBytPesQAx14-GPR6a67ZEbwbiPFC84Oa1eZjfcFgByD48NMdqEhg0c_tU2eJNS0xLm_kt7S2p8FtWvXLOrFXEKZMS1lgt6BAcjFLF_PYoEskePlsMP5tOsxc_0WupF?purpose=fullsize)

| Screen                    | What users should see                                                     | Main actions                            |
| ------------------------- | ------------------------------------------------------------------------- | --------------------------------------- |
| Application dashboard     | Requested limit, review stage, missing documents and next steps           | Continue application, provide documents |
| Active-facility dashboard | Approved limit, outstanding principal, pending draws and available credit | Request draw, make payment              |
| Draw request              | Amount, purpose, destination, requested date and applicable terms         | Review, submit                          |
| Draw history              | Requested, approved and funded amounts with processing status             | View draw, track transfer               |
| Availability              | Explanation of available credit, holds and applicable restrictions        | View calculation, resolve requirements  |
| Payments                  | Amount due, due date, scheduled payments and history                      | Schedule payment, view receipt          |
| Reporting obligations     | Required documents, covenant reviews and deadlines                        | Upload, respond                         |
| Statements                | Period balances, draws, repayments, interest and fees                     | View, download                          |

**Evaluation of your current implementation**

Your source includes an eight-step application, a record table with intake-edit controls, explicit field definitions, and navigation for offers, draws, availability, payments, covenants and collateral. These are useful foundations. [Source: Xenhey Business Lines of Credit](https://www.xenhey.com/api/store/928D48344AF64AF68F28113A10AE3346).

| Finding                                                                        | Recommended improvement                                                                   |
| ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| Dashboard shows fixed “Underwriting,” “2 needed,” and “Sep 12” values          | Derive these from the selected application                                                |
| Requested amount comes from the first record in the collection                 | Bind all dashboard information to the selected customer/application                       |
| Customer dashboard displays a general application table, including risk tiers  | Scope records to the authenticated business; keep internal risk assessments in operations |
| Intake table supports Edit, but dashboard table lacks a direct record action   | Add Continue/View Application links carrying `recordId`                                   |
| Changing wizard steps redraws the form                                         | Preserve current edits before navigation                                                  |
| Selected records are reloaded from their original `formData` when steps render | Maintain a working application draft so revisiting steps retains changes                  |
| Main Save Draft captures only the active step                                  | Save the complete application and current step                                            |
| Form submissions save under a shared form key                                  | Merge by application ID and update the corresponding table row                            |
| Final-step submission uses the same generic browser-storage handler            | Validate the complete application and confirm backend submission                          |
| Checkbox hydration uses `Boolean(value)`                                       | Parse saved values explicitly so `"false"` does not become checked                        |

**1. Active credit-line dashboard**

Show application progress before approval. After activation, use a facility summary.

*Illustrative values only:*

| Metric                 |       Example |
| ---------------------- | ------------: |
| Approved limit         |      $250,000 |
| Outstanding principal  |       $85,000 |
| Pending draws reserved |       $15,000 |
| Available to request   |      $150,000 |
| Facility maturity      | June 30, 2027 |

Place **Request a Draw**, **Make a Payment**, and **View Statement** below the summary.

The example assumes no additional restrictions. In production, display provider-confirmed availability, including any applicable collateral limits, holds or restrictions. Show the last update time.

**2. Draw-request UI**

Use a focused form with a persistent facility summary.

| Field            | UI behavior                                |
| ---------------- | ------------------------------------------ |
| Facility         | Select the applicable active line          |
| Requested amount | Currency input with permitted limits       |
| Use of proceeds  | Purpose selection and explanation          |
| Destination      | Verified, masked business account          |
| Requested date   | Available dates and processing information |
| Repayment source | Required explanation where applicable      |
| Certification    | Relevant agreement acknowledgment          |

Before submission, show:

* Requested amount and applicable charges
* Estimated proceeds and delivery timing
* Availability after the proposed request
* Outstanding approval requirements
* Terms applicable to this draw

Distinguish **request submitted**, **approved**, **transfer processing**, and **funded**. Recheck availability on the server and prevent duplicate requests.

**3. Draw-history UI**

*Synthetic records:*

| Draw      | Requested | Approved |  Funded | Status       | Action |
| --------- | --------: | -------: | ------: | ------------ | ------ |
| DRAW-1001 |   $25,000 |  $25,000 | $25,000 | Funded       | View   |
| DRAW-1002 |   $15,000 |  $15,000 |       — | Processing   | Track  |
| DRAW-1003 |   $10,000 |        — |       — | Under review | View   |

Selecting a draw should show its purpose, destination, approval history, funding reference and related charges. Missing approval or funding values should display as pending, not zero.

**4. Application and offer UI**

Retain your existing eight application sections:

1. Business profile
2. Credit request
3. Activity and repayment
4. Financial profile
5. Collateral and debt
6. Ownership and control
7. Documents and review
8. Consent and submission

Add a final summary with **Edit section** links and distinguish requested terms from lender-issued offers.

Offer comparison should show approved limit, pricing structure, fees, maturity, repayment requirements, collateral, guarantees and conditions where applicable. Terms should come from approved provider configuration.

**5. Payments and availability**

The payment screen should distinguish principal, interest, fees and total due. Show scheduled payments separately from posted payments.

Do not automatically increase available credit when a payment is merely scheduled. Refresh availability from the servicing system after processing.

For facilities governed by eligible collateral, add an availability explanation showing:

* Current eligible collateral value
* Applicable advance calculations
* Facility cap
* Outstanding usage
* Pending commitments
* Reserves or restrictions

Only show this panel when that facility uses such a structure.

**6. Reporting and renewal workspace**

Translate the existing covenant navigation into understandable tasks.

| Requirement            | Period               | Due date | Status        | Action         |
| ---------------------- | -------------------- | -------- | ------------- | -------------- |
| Financial statements   | August               | Sep 30   | Requested     | Upload         |
| Receivables aging      | September            | Oct 10   | Not submitted | Provide        |
| Annual facility review | Current review cycle | Nov 15   | Upcoming      | View checklist |

Use the actual agreement’s requirements. Uploading evidence should move a task to **Submitted for review**, not automatically to **Compliant**.

For Xenhey, prioritize **complete application saving → customer-specific dashboard data → active-facility availability → draw review and tracking → repayment and reporting workflows**.
