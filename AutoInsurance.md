Your [Xenhey Auto Insurance page](https://www.xenhey.com/api/store/3540E41F455C4C6BB054DEFDAE1D46B7) opens a **Customer Dashboard** with quote records and intake-edit controls. The strongest improvement is to organize the experience around **drivers and vehicles → coverage choices → comparable quotes → confirmed policy → ongoing service**.

I reviewed its HTML and JavaScript. I did not submit quote requests or test separately linked pages, carrier feeds or binding integrations.

**Auto Insurance UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/RDC7exPXpnILKxoQ3dM0M3mWc4V2ZT6M6bDvfsfnu5A9dSrdS6g3AxVe0XWm8yhvTgjYs8Rb4QApn5M9y0PL3iztuu13sWeSnV1b7--Y1d5tmYzw-K1TrpVVractQtItmY2v9KuUWDfVBV2mrRG64g1eTOgw67Wzh1Xa8BOalOY1FbOnqSYfnFrYSfQSZ76O?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/9_rx044m8FQvkPZS0umqPcq21Ohi0cVXb0rU-RTk0YP9EbVTkMAG1Tzj38IOEQGfVq1Hu9hEsOLkS1kNeOa56aldhA3aFLhfGc1HK3z8WbC5mlQTwzj6qS_55XCRzBsw2OrpwQv32YU5mtrA7noXoGLXQiPxPGjnI9zYMMQeamK7tES_HYj1uDAUoecWNHk9?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/CESX9iJvWRLqfUcnF_d6m1SIUwebejnmVzof5t3wUMZk4EkMfjt49nDFnefpU5ajvbPeiiZ9aopHTYyI6oHuP4D3mDAsEKlVHAjgi32rq3SGGUdx1IG6uH4oqTFk5iJtrUk_zMqYDIet9ABgzTTejyu9dPxwOa7bxrg8OCVh5UxQ8TAMIhUBJimPPrt6saXB?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/YyBoMJgZU5emJsn00l1OgL-3voz-jM79yY-6-plJ6ozTuZ8wlsW27bzz5_UgmYXm7jU5s56gd9uelaKC3jDJVcJVZU562tsm8xQpo0oOTiMpbDKeBb7_muP4pJSwo7vvri_xXhOALsd4_GLwJuxlHnCcW0mh3onoBKjcFp7jFpQuO8x7YOXWyXqoy5_CVScQ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/emy8QOuHgHo86jBVXVgBxxwqyBqFR4Ti15yeTxWuSthiykvSVpKcBfdAmzhfBi7S7yvdm4Qaii6Fvh0o0ilcnGjS3G31k-tacNRkQFkAWU7ZKNBUqYIENpgXL1CZQunOy1QySoIIwZa8ZAqchuRuTq6_t7soKNjjASLsMgIPIJHEmQIzXQxeex_WkXnMXzgg?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/S_rA5uyfraeG4XajlalTs6Yor96-BiOQ1GAyyDgysyy9C-5F9ToUsQrbaqIKn5eTld4KR-L70kQNieXdbtekeIKeN115rIVY4jq1Zy2fngYf6d9865-nWbe08WmmUW6Wt_KldWMMdAzH9DfoSmYQf_Raz_RK3NYu6KPZiy86Nt8JiN-BFLn2U9nqZaWQSQRF?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/shlIFQpLm558Aw-L3jmLy_TVqckRDfpaKT-z4JM6ct4FNqcW0KAFvT4YoCsoncx9BYQdWFc5kXlUBFbPP-eMhlFn8EJmoTJlRblaXZRs007kykhY3Xe4s2lUbjNdU-XWsLGRorRfdUo2r7Wy3XA1YMU8vwSNgvQC7kzHAuzqFvgGCW7cFeGBKYsQubxGYQ31?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/redtMA_m9gHDBa6N4eVRw1tULiXi5I98QAamFgwt5UcgkYGetTxVVcisoVGlAwqxYErK6yjWQIq5pXAxmW_l-AqEDnCtQ3M4MKyUAXOVDbsXvIB8SNouBveaf1wpKdfQIGumPoF19KmRVSdTHbPU-TKunSCPtJhMoOOX8mvLUSR-beHQkyQIgvrG4nzjXyzL?purpose=fullsize)

| Screen              | What users should see                                                    | Main actions                   |
| ------------------- | ------------------------------------------------------------------------ | ------------------------------ |
| Customer dashboard  | Quote progress, insured vehicles, policy status and next action          | Continue quote, view policy    |
| Driver profiles     | Household drivers, vehicle assignments and verification status           | Add driver, edit               |
| Vehicle profiles    | Year, make, model, ownership and usage                                   | Add vehicle, update            |
| Coverage selection  | Coverage limits, deductibles and optional benefits                       | Adjust, compare                |
| Quote comparison    | Carrier, policy term, premium, payment schedule and coverage differences | Review, select                 |
| Policy confirmation | Confirmed coverage, effective date and carrier documents                 | View documents                 |
| Policy management   | Vehicles, drivers, renewal date and change requests                      | Request change, manage billing |
| Claims and support  | Carrier contact, claim reference and available status                    | Start carrier handoff, track   |

**Evaluation of your current implementation**

The page already includes vehicle-specific quote rows, field-specific choices, explicit boolean serialization, searchable tables and CSV export. Its carrier comparison identifies providers as synthetic, and its product copy distinguishes preliminary intake from binding coverage. [Source: Xenhey Auto Insurance](https://www.xenhey.com/api/store/3540E41F455C4C6BB054DEFDAE1D46B7).

| Finding                                                                                        | Recommended improvement                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| Dashboard totals are fixed: six quotes, two drivers, two vehicles and one policy               | Calculate totals for the selected customer                                                                 |
| Quote rows display an estimate followed by `/mo`                                               | Include estimate status, policy term, total premium, initial payment and installment fees where applicable |
| Intake keeps all sections in one form                                                          | Preserve this approach; values remain when switching sections                                              |
| Save Draft runs full required-field validation                                                 | Allow incomplete drafts                                                                                    |
| Submission saves a separate browser-storage object                                             | Update the selected quote-intake record and refresh its table row                                          |
| Carrier Review links all open the same page without a carrier identifier                       | Carry the selected `carrierId` and quote context                                                           |
| Quote-status milestones are hard-coded                                                         | Populate them from actual responses and customer actions                                                   |
| Coverage choices include “Full coverage” as a liability option                                 | Replace this ambiguous label with explicit limits and individual coverages                                 |
| Collision and comprehensive fields default to required checkboxes in the generic coverage form | Apply conditional requirements from the actual product configuration                                       |
| Edit hydration uses `Boolean(value)`                                                           | Parse saved values explicitly so `"false"` does not become checked                                         |

**1. Customer dashboard**

Provide two clear dashboard states.

**Shopping for insurance:** show the selected vehicles, intake completion, missing information, carrier responses and next step.

**Managing an active policy:** show the carrier, policy reference, effective and expiration dates, insured vehicles, billing status and policy documents.

Do not count a quote selection as an active policy. Display coverage as active only after confirmation from the carrier or authorized binding system.

**2. Driver and vehicle workspace**

Use separate, repeatable cards rather than relying only on household counts.

| Driver card                | Vehicle card                                  |
| -------------------------- | --------------------------------------------- |
| Name or display reference  | Year, make and model                          |
| Household relationship     | Owned, financed or leased                     |
| Driver verification status | Personal use, commuting or other declared use |
| Assigned vehicles          | Estimated annual mileage                      |
| Information needing review | Garaging location summary                     |
| Edit / remove request      | Edit / remove request                         |

Retain your prototype’s secure handoff for license numbers, full VINs and verification evidence. Use synthetic records for demonstrations.

**3. Coverage-selection UI**

Display coverage as separate rows with explanations and configurable choices.

| Coverage component              | UI control                                         |
| ------------------------------- | -------------------------------------------------- |
| Bodily injury liability         | Explicit available limits                          |
| Property damage liability       | Explicit available limit                           |
| Collision                       | Include/exclude where permitted, plus deductible   |
| Comprehensive                   | Include/exclude where permitted, plus deductible   |
| Uninsured/underinsured motorist | Available options for the applicable configuration |
| Medical payments or PIP         | Applicable options                                 |
| Rental reimbursement            | Available benefit and limits                       |
| Roadside assistance             | Optional selection where offered                   |

Avoid labels such as “Standard” or “Full” without showing exactly what is included. Keep collision and comprehensive deductibles separate.

**4. Quote-comparison UI**

Compare quotes using the same vehicles, drivers, coverage period and requested coverage where possible.

| Comparison field  | What to display                                          |
| ----------------- | -------------------------------------------------------- |
| Carrier           | Name and quote reference                                 |
| Quote status      | Preliminary, verification required, or carrier-confirmed |
| Policy term       | Start date and duration                                  |
| Total premium     | Premium for the full quoted term                         |
| Payment plan      | Initial payment, installments and applicable fees        |
| Liability limits  | Actual quoted limits                                     |
| Deductibles       | Collision and comprehensive separately                   |
| Optional benefits | Included, excluded or unavailable                        |
| Differences       | Coverage variations requiring attention                  |
| Validity          | Quote date and expiration, if supplied                   |

Highlight coverage differences before emphasizing price. Use carrier-supplied pricing rather than calculating a monthly quote from incomplete intake data.

**5. Quote editing and submission**

Use this sequence:

1. Select **Edit** on a quote-intake record.
2. Load all fields while preserving the record ID.
3. Save changes to the shared record collection.
4. Update applicant name, vehicle summary and timestamp in the table.
5. Mark previously returned quotes as potentially outdated.
6. Request refreshed quotes through the configured integration.

Changing a vehicle, driver or coverage preference should not silently retain an old premium as current.

**6. Policy changes and service**

After policy issuance, provide:

* Policy and insurance-card documents supplied by the carrier
* Driver and vehicle change requests
* Billing and renewal information
* Coverage-change requests
* Carrier claims handoff
* Support history

Distinguish **change requested**, **under review**, and **effective**. Saving a request locally must not imply the policy has changed.

For Xenhey, prioritize **complete draft saving → customer-specific quote records → repeatable driver/vehicle profiles → explicit coverage choices → comparable carrier quotes → confirmed policy status**.
