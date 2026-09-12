Your [Xenhey Invoice Factoring page](https://www.xenhey.com/api/store/A8233A3E823E42BEB0D76D07DD12A5F2) includes facility applications, invoice eligibility, advance offers, reserves, collections and settlements. The main improvement is to make **individual invoices and their money movements** central to the interface.

I reviewed its HTML and JavaScript. I did not submit invoices, initiate funding or test separately linked pages.

**Invoice Factoring UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/Uuk7GUc_LNE82gVHeCmkqD117yCHOyjRDuXJDbZ9rqXnvqLWdM9-Obf3HNbZ3rKKs7W98lVCSlVIS4Xrprk0qH3OGkHvbVNwVzZ4AAZmhglirmR26w-oEM67-CleAu97pPNUmbU2FE0Kgwzj50l8niUc2mJ5c6fGlh062RdHuCQUH8VdGj6V0bkmx_zF6pru?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/tdFXOzYATvpIHSsXTirPeNH9L1wsphGLXAR7HpFzJ8CLmxC7LSc1g1LIGdlseZw6cXhFx2n6B5BYHzAsSn0DgkrSwluEcVrv_Hl0m3pSUw3fmyH6fbPNkMlXTnbAKhsYWMszg8tPI552gDRo1S_-cWdtz0mw2M-2M_bs247iSWhUlWw_k465ji-ODnzXvw3l?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/_PpGI0ZOG0GUk2TZTgPqdzVhhQUisVIkzD-kVXznuG5HuXhb2l6tqiTz1hmXjm8kiAZsaUYmHJEPeFm1ODHsbmjsDlwO6Cxb15kPwi4HISDdjd2eTujnae4uOOp1Alui9CYcqnwomTwZXfC5iaoeTuTiM9kVcmQSm-UCUpRu04MWOwLUKVT8kWDYr43p0sXZ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/wFYnHIuv3WjR4Q8wl3EphKLTkQII7qeT59CxfplLdtDS0NivAXMFAdpo6vJ2jt-kXsvaONBtpuG6VUeTAjJ3dqOwDKfdPItKxXfrSnZL5xMy3jd1pj3CDfO0UYfs-PXWc3q_COKlT5HDr91-KuL21Ivf7hefNveGDvfYI1sTD098ZqBFGV2dSoknu5G_ArUl?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Id1PxVxysJN5aHfypbstwacBtZfLnXUXPfzwuTfJ5fF3_8OS72-9lhhJoHqqN8KHHCmfF6HOJzQiqBIyvNj1PAOK9hT4_P2VjJ9diddYa5DFPxt95471ro9YmJaNDcfEzmjislJJ4EUrRmujZRTKLl581gfxSRQcSyOpQ7ast2xS6m1WlD3WSj9iJd9KRumo?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/7VSi3Z79LEheetPSnGxNMxhIW-FMvux-H_eZVXKzwXM4LFvTDKK064zCwwgrbpYMhnZS9nN-eaxkTes2Yu3tIYOWtFaLWgoonvkfYiAvjR3Ea90-F3zk4L7uNo6vJLfxfGE1A8P3Rn-goe00l744t0TjVMoxxAkMYcAM-VxEHHbAO-WabUOII1PApal1XXt-?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/bvJ86coGRtVcOtQSlC1mRIyyQk-YJgzvjAaH-54dmdRk0TsWxjFT0pK4-3Hqeg-Ilq9EOprCBINf5-ewOWmr6yub41q8aaCWqE1YPZ8JUm_1ymqlF1SZ3uSh6TpG5l_C3QjtG_NEuGi2ED3UuMzwFf5glsQaswomUAHMe4R2MeymKVw4Ew0PCx1g7HyUVnp3?purpose=fullsize)

| Screen              | What users should see                                                         | Primary actions                  |
| ------------------- | ----------------------------------------------------------------------------- | -------------------------------- |
| Client dashboard    | Facility status, eligible invoices, funding requests, reserves and exceptions | Submit invoices, resolve issues  |
| Invoice submission  | Invoice rows, debtor, amount, dates and supporting evidence                   | Import, validate, submit         |
| Eligibility results | Eligible amount, excluded amount and specific reasons                         | Resolve exception, review offer  |
| Advance offer       | Selected invoices, gross advance, deductions and expected net proceeds        | Review terms, accept             |
| Debtor customers    | Outstanding invoices, payment history and applicable limits                   | View debtor, update information  |
| Funding history     | Batch, approved advance, deductions, transfer status and confirmation         | View funding details             |
| Reserve ledger      | Amounts withheld, adjustments, releases and remaining balance                 | View entries, download statement |
| Collections         | Due dates, aging, payment promises and disputes                               | View activity, respond           |
| Settlement          | Collections received, advance cleared, fees and reserve release               | Review allocation, download      |

**Evaluation of your implementation**

Your source defines a ten-step intake covering business, ownership, facility request, receivables, debtors, performance, existing financing, collections, documents and authorization. It also provides administrative screens for concentration, dilution, invoice verification and funding review. [Source: Xenhey Invoice Factoring](https://www.xenhey.com/api/store/A8233A3E823E42BEB0D76D07DD12A5F2).

| Finding                                                                                             | Recommendation                                                                            |
| --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------- |
| Dashboard figures are fixed: $500,000 facility, $188,400 available, 47 invoices and $31,600 reserve | Calculate values for the selected client and show an “as of” timestamp                    |
| “Available” has no explanation                                                                      | Identify whether it means facility headroom, eligible advance capacity or confirmed funds |
| Invoice, debtor, eligibility and settlement screens reuse application rows                          | Create separate datasets and identifiers for each record type                             |
| Invoice submission supports one generic invoice form                                                | Add batch upload, row-level validation and an editable preview                            |
| Advance offers and reserve balances appear as editable forms                                        | Display provider-calculated results with authorized actions                               |
| Name-based field typing makes fields such as `reserveStatus` numeric                                | Replace inference with explicit field types and allowed values                            |
| Wizard navigation redraws fields without retaining current input                                    | Save before navigation and restore every section                                          |
| Main Save Draft stores only step and timestamp                                                      | Persist the complete application under a stable ID                                        |
| Step saves overwrite the same intake key                                                            | Merge section data                                                                        |
| Final submission logs a fixed reference and displays a toast                                        | Validate all sections and confirm backend submission                                      |
| Client and application links omit record IDs                                                        | Load the selected client/application rather than fixed sample details                     |

**1. Client dashboard**

Organize the dashboard around the client’s next action:

* **Invoices awaiting submission**
* **Exceptions needing information**
* **Offers ready for review**
* **Funding in progress**
* **Collections awaiting allocation**
* **Reserve releases**
* **Upcoming and overdue invoices**

Keep facility onboarding separate from recurring invoice funding. An active client should see current invoice batches rather than a permanently fixed application-progress tracker.

**2. Invoice submission and editing**

Use an editable table with a details panel.

*Illustrative records:*

| Invoice  | Debtor customer    | Invoice amount | Due date | Evidence                  | Submission status |
| -------- | ------------------ | -------------: | -------- | ------------------------- | ----------------- |
| INV-1042 | Metro Distribution |        $25,000 | Oct 12   | Complete                  | Ready             |
| INV-1043 | Northstar Retail   |        $18,500 | Oct 18   | Delivery evidence missing | Needs information |
| INV-1044 | Harbor Logistics   |        $12,000 | Oct 20   | Complete                  | Duplicate review  |

Recommended workflow:

1. Upload a CSV or import from the accounting system.
2. Map columns and preview invoices.
3. Check required fields, duplicate references and debtor matches.
4. Attach secure evidence references.
5. Correct flagged rows.
6. Review batch totals.
7. Submit and receive a batch reference.

The **Edit** action should open the selected invoice, preserve its ID, save changes and refresh that same row. Submitted invoices should use controlled corrections with change history.

**3. Eligibility-results UI**

Show why an invoice is fully eligible, partly eligible or held.

| Invoice  | Submitted | Eligible | Status   | Explanation                |
| -------- | --------: | -------: | -------- | -------------------------- |
| INV-1042 |   $25,000 |  $25,000 | Eligible | Review complete            |
| INV-1043 |   $18,500 |        — | Pending  | Delivery evidence required |
| INV-1044 |   $12,000 |        — | Held     | Possible duplicate         |

*Illustrative results, not financing terms.*

Distinguish **pending review** from **ineligible**. Do not display missing eligibility data as a confirmed zero.

**4. Advance-offer UI**

Show the calculation clearly before acceptance:

| Offer component   | Display                                                     |
| ----------------- | ----------------------------------------------------------- |
| Included invoices | Invoice references and eligible amounts                     |
| Advance           | Approved rate and calculated gross advance                  |
| Deductions        | Each applicable fee or adjustment                           |
| Net proceeds      | Amount expected to be transferred                           |
| Reserve withheld  | Amount retained under the agreement                         |
| Terms             | Fee basis, timing, recourse provisions and other conditions |
| Validity          | Expiration and unresolved requirements                      |

Use provider-issued terms. Keep **estimated**, **offered**, **accepted** and **funded** amounts distinct.

**5. Reserve and settlement UI**

Replace the generic reserve form with a ledger.

| Date   | Reference         | Entry type       | Increase | Decrease | Running balance |
| ------ | ----------------- | ---------------- | -------: | -------: | --------------: |
| Sep 12 | Batch B-1001      | Reserve withheld |   $5,000 |        — |          $5,000 |
| Oct 12 | Settlement S-1001 | Fee deducted     |        — |     $500 |          $4,500 |
| Oct 12 | Settlement S-1001 | Reserve released |        — |   $4,500 |              $0 |

*Simplified synthetic example; actual allocation follows the agreement.*

Each settlement should link the debtor receipt to the invoices paid, advance cleared, fees, adjustments and reserve release. Support partial payments and unapplied receipts rather than assuming every invoice settles in one payment.

**6. Collections and operations**

For clients, show invoice aging, collection status, disputes and information requests.

For authorized operations staff, add:

* Debtor verification and limits
* Concentration and dilution exceptions
* Duplicate-invoice checks
* Funding approvals
* Collection allocation
* Reserve adjustments
* Settlement reconciliation
* Assignment-notice status and evidence

Saving a notice status should not imply a notice was sent. Likewise, accepting an offer should not mark funding complete without transfer confirmation.

For Xenhey, prioritize **reliable intake saving → batch invoice submission → record-specific editing → eligibility explanations → advance and reserve accounting → settlement reconciliation**.
