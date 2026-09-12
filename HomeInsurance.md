Your [Xenhey Home Insurance page](https://www.xenhey.com/api/store/FC166D54D41C4EF8B392D4731491FB9D) opens a **Customer Dashboard** with quote records and intake-edit controls. Its strongest opportunity is to make **the property, coverage details and quote differences** central to the experience.

I reviewed its HTML and JavaScript. I did not submit quote requests or test separately linked pages, carrier feeds or binding integrations.

**Home Insurance UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/Hu4KhJbCtX3ZsYFPF2nqXle_E3eXJYVeIytlHjCwX-mL8uPEgpmpOyy0NYNuxGUxXFnoK0NxIUrLIR5aJMC6tNo45_ndxgxOq3P911-E2_SNWKFtGLO3Qg9I3zQeGv_5unIkWcv36huEKgp-vnwVHZcY4C7vp31Wr1yavWH3zTUnJ1k5mPpcRGV-AYzY7SjJ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/AqHkiDXKdM7ZB9rYeeUzKFFF24jPOCCESm6jn5ia1lZntL1BTaYxl7nUHHaKGl8cBLVXmS4geR8Yul2QPuxoODRqtLlquX9_dNSqLQTKiX_yBymPk4t3Tll6om7pyzVqyi_G1fTy0eaPTlx7fDyz62Bw5wrKaBVKrw00yEvnBKXMghUVFg2VTo3HdHd9L82S?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/7KxgQVzPky7e3XPiw07cHeGEskrR9HEXDCIhqME1MSs0z7aD2QC_-6qHAeAVuBB-x0BlcfBAnc99Gl7z2ePC_3dEpLHFNknZWoSwUE2JGCS4ht4iGeMYxYdGi8BGDPgsvriVdv99BmouZO622E_9K6LERZ0-QxmcssNArjV2Y8XDTjrrySLRiULqK5JcHyDd?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Vw6BfaXvGpOX5eL4gK8LzqAwJ1BAbjvTVxoFTQQp9E9Pgp8btjLhyDs8j3EDuVkIBlg-8SGMbor2EgU0X4nyvveGZQKcMy-EC4EbL43IuLrMajSYqX3faoRbEi_immtFWmD3CTlqAwMr1b7gjr0LkZMw-N0k7SCUArRSRHe8r0MNXjhRVipuDGYClHWMG4wc?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/fapgHhTU28NsStdVsDXUMlg3BSHo4WyJPIqLIxSMrn5nvdv-wkI8KZJ4Rd6qVAlec24uzPCUSX2lMscCJMMnkiKjcjHzUEdw3t71-IkzZVpRy8mnBQu0hRGa8I2tZ5VgBlZ8XQTPQ52NlRd2NQpv1-MCm8Y4YviAgqx5HvP0pY31UAUASBNglER9nQX6llH8?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/htIPXPyg2GUYLwGFRUKe7QKsyVtKxOfL2Rseesr1v2HUob9cHXTCfECawAWb_paej9BRTbWeOwRQy_ts4U5HZnxSB5P4awxE7TQnH4ebzbt3x6NXzFS3E7Vd4f1s_IGkDUGnEaquhcBIx_vD_RJEdhxO5NuxLpa5Sla_IT_WCj7vHGHuWPCzxW3Oa5nt7z-j?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/abY8nJLlRhYFA-JPQ8vtsM-IBXXIowHaFHj2stgfEkTrW3i88cDF6I3tNf3WuIU1DuKuCGQ8VdZgkfh2CYbDI7STqK-YKceWP3C_lTxTk602_V_yvKEPb6v-y5HlqBqVTcI4N9cDVEm_01EEVOLi4XoaaHj_Wu5B5_89W87schDXACfNolco2dt5UB4H4Une?purpose=fullsize)

| Screen             | What users should see                                                | Main actions                   |
| ------------------ | -------------------------------------------------------------------- | ------------------------------ |
| Property dashboard | Home summary, quote progress, outstanding requests and policy status | Continue quote, view policy    |
| Property intake    | Dwelling, occupancy, construction, roof and home systems             | Edit property, save draft      |
| Coverage builder   | Dwelling, belongings, liability, deductibles and optional coverage   | Adjust preferences             |
| Quote comparison   | Carrier, term premium, coverage limits, deductibles and differences  | Compare, review                |
| Document readiness | Requested evidence and secure submission status                      | Open secure upload             |
| Policy management  | Confirmed coverage, effective dates, billing and renewal             | View documents, request change |
| Claims support     | Carrier contact, claim reference and available updates               | Open carrier claims service    |

**Evaluation of your implementation**

Your seven-section intake already covers property characteristics, roof and systems, replacement-cost preferences, belongings, liability, deductibles, risk history and consent. Keeping all sections inside one form also preserves entered values when users switch steps. [Source: Xenhey Home Insurance](https://www.xenhey.com/api/store/FC166D54D41C4EF8B392D4731491FB9D).

| Finding                                                                                    | Recommendation                                                                 |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| Dashboard counts are fixed: six quotes, one property, two household members and one policy | Calculate values for the selected customer                                     |
| Estimates display only as `/mo`                                                            | Show total term premium, billing schedule, initial payment and applicable fees |
| Save Draft requires every required field to be completed                                   | Allow incomplete drafts                                                        |
| Submission writes a separate browser-storage object                                        | Update the selected intake record and refresh its table row                    |
| Carrier Review links omit the selected carrier                                             | Carry `carrierId` and quote context into the next screen                       |
| Quote-status milestones are hard-coded                                                     | Use confirmed workflow events                                                  |
| Source contains leftover auto/renters schemas, including auto-specific discounts           | Remove or isolate unrelated schemas; define home-specific discount choices     |
| Replacement-cost input offers only six fixed amounts                                       | Add “Unknown / needs assessment” and support provider-reviewed values          |
| One valuation-method field covers the entire request                                       | Identify valuation treatment separately for applicable coverage components     |
| Checkbox hydration uses `Boolean(value)`                                                   | Parse saved values explicitly so `"false"` remains unchecked                   |

**1. Property-centered dashboard**

Use a property summary card beside the next action:

* Dwelling type and occupancy
* City and state
* Construction and year-built range
* Roof material and age
* Selected coverage preferences
* Quote or policy status
* Last updated time

During shopping, prioritize **Continue quote**, **Review requests**, and **Compare quotes**. After policy confirmation, prioritize **View policy**, **Billing**, **Renewal**, and **Request a change**.

**2. Guided property intake**

Retain the current seven sections, with clearer conditional questions:

1. Applicant and property area
2. Dwelling and occupancy
3. Construction, roof and systems
4. Replacement-cost and belongings information
5. Coverage preferences
6. Risk history and additional-coverage review
7. Carrier selection and consent

Adapt questions for condominiums, manufactured homes and seasonal residences. Provide “Unknown” where customers may need an inspection or specialist assessment.

Add a final review summary with **Edit section** links. Keep exact addresses and supporting documents in the secure provider workflow described by your prototype.

**3. Coverage-builder UI**

Present each component separately.

| Component           | Recommended controls                                   |
| ------------------- | ------------------------------------------------------ |
| Dwelling            | Requested limit, estimate source and review status     |
| Other structures    | Structure list and requested limits                    |
| Personal property   | Value range, valuation preference and valuables review |
| Loss of use         | Available limit and relevant terms                     |
| Personal liability  | Explicit available limits                              |
| Medical payments    | Explicit available limits                              |
| Deductibles         | Amount or percentage, basis and applicable event       |
| Additional coverage | Available options and included/excluded status         |

Do not treat a customer-selected replacement-cost amount as a verified valuation.

For percentage deductibles, display the calculation basis and dollar equivalent when the quoted terms provide enough information.

**4. Quote-comparison UI**

Compare the same property and requested effective date, while highlighting differences.

| Comparison field | Display                                                     |
| ---------------- | ----------------------------------------------------------- |
| Carrier          | Name and quote reference                                    |
| Status           | Preliminary, verification required or carrier-confirmed     |
| Policy period    | Effective date and duration                                 |
| Premium          | Total quoted term premium                                   |
| Billing          | Initial payment, installments and fees                      |
| Coverage limits  | Dwelling, structures, belongings, liability and loss of use |
| Valuation        | Applicable settlement basis by coverage component           |
| Deductibles      | General and separately applicable deductibles               |
| Additional terms | Endorsements, exclusions and unresolved requirements        |
| Validity         | Quote date and expiration, when supplied                    |

Make coverage differences visible before emphasizing the lowest price. Use carrier-supplied terms rather than estimating coverage from generic labels.

**5. Intake editing and quote refresh**

Your existing Edit controls provide a useful starting point. Complete the workflow by:

1. Loading the selected record with its stable ID.
2. Saving all form values to the shared record collection.
3. Updating applicant name, property summary and timestamp.
4. Refreshing the same table row.
5. Marking earlier quotes as potentially outdated when rating information changes.
6. Requesting refreshed quotes through the configured integration.

A changed roof age, occupancy or coverage limit should not leave the previous premium displayed as current.

**6. Policy and operations workspaces**

For customers, show confirmed policy documents, effective dates, billing, renewal and change-request history. Distinguish **change requested**, **under review**, and **effective**.

For operations staff, organize queues around property review, replacement-cost assessment, roof/system questions, coverage differences, document requests and carrier responses. Saving an internal status must not imply coverage was bound.

For Xenhey, prioritize **home-specific schema cleanup → reliable draft saving → property-specific records → explicit coverage comparison → refreshed quotes → confirmed policy status**.
