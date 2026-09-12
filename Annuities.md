Your [Annuities page](https://www.xenhey.com/api/store/4D2A41AE60A643EF96547DD3C81DDAF4) provides a useful **consumer discovery and contract-review workspace**. I recommend emphasizing income goals, access to money, product comparisons, and replacement analysis.

I reviewed the HTML and embedded JavaScript. I did not submit information or test linked pages, carrier integrations, or contract issuance.

**Annuities UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation or verified insurer functionality.

![Image](https://images.openai.com/static-rsc-4/3GXUw9Jg9_h190WYQpQdjBsoamu7y0kNo_EXnk0ul-NTIPdy3eIJlSb5v0ie015FkCM4aoNtTUn_F13C7ByUc7gcnFPE4dEPYR4DChmnZvimSXsWKtmRPrh6ow-OMYg7gkuVcvkR5wPqkxEWVlua26jP_7TsawFRWVPuM20ku6rzf5EUtnP3HTkkKWDtUXgE?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/b46FkmllQXSERlFLVUgupcTJroMBwxQ2u-ChJsJjJ33_Q8YepqDvmyzWCH7idgyjf1QI5m4sGzTVSN6FpegA2xjjG0MD72OWy9-MnKaYdQLwQitZcPDv8KBOT2fN1PbbDnT78LP5yvxFnK0iP27SaJnR6BQX23f7wo-VpQk4XJeTui8JCyYYiM9t_j5yJJkJ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/py7jli2vgG3GskTnZhNT4Ado6LJhQY_zYa_Wltyle3Wek9se-BHQRg9eebQOQeoUBj9hM0ff_Am5QN94ZgdFfHQ6wHnrSumcBDPwZRHfR8xT9TaEJ93pxfJGVh8qhDGNmCX6r8PE8UHiF4S_Icz363TYzi-jh519s4jT1VU8Dza-7qQiRn2sEJc4gabGMDcd?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/DXaIJHvyiMPBhCd4G16jkETTPbGCjhL8abCsBEGSN-3Wo0Ape6VNlXvx73jtzv80Oez0B2yUgMinW1SM2rPXzB0ywgkBQjPVsANCXOK65DtbvpR8JHPV-jREznX0d8sCzZwSl6sE1R12AiXkBLgV8LiO5DQQva2Fxmj-emjA_8r5Z19TpPHTbiJDWPbJqN1-?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/tuM2tNFi040F59LYXh-RyxrdLeZceP7N60UH-UhOWWK9xi88z-prQKf833pSdWBl1GTVEGIeRiFfikDydhcct_3a4y6HtfpYAQVvUmYM_baTPSqvDzU7fLoNHHqdZp_gHKoTevbZ8bZ1pw6r1MwQphPsMOiR6qCdtMbLVAEZj4aQ7i3QQG2HdoQlT5ThTZFn?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/HYCbJD03qfJYUMHraIuHiMyLhjtfMhOdRIDL9BU3IcoBvNnk79imgSKMwmmTuC9vklkykEt8PvpsnnGU8mutElqgpmiLx7LTyWoqVsxnweNt7TB0t6P4W-STT9KqMxn0Ygtoac02greLFtd8nMCoyo1cFfrZKcOBkiepeC_S0eqCXrs5wdmiaITAd8CZlqnt?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/YQ9tylkmKQILw9i7iLXQ13_118V1WlwU3GDuozOqYy7wTeVsL3rRm6JNPzcaIqf07zhpbBlDB5l8QtixcK6cVnO9zJ97VqaLDOkLfQKAExJffXz1F1TfKpub43cAaWBk8roaf8pUP6qBtlSWT_u1Pcqejd7XZzz4h5MpInC0VttAUqegzqQxHXQZKt4TPXM_?purpose=fullsize)

| UI example                     | Recommended content                                                                                       | Primary action            |
| ------------------------------ | --------------------------------------------------------------------------------------------------------- | ------------------------- |
| **Consumer dashboard**         | Profile completion, outstanding questions, assigned specialist, application stage                         | Continue profile          |
| **Income-goal intake**         | Premium range, desired income start, payment frequency, liquidity needs, other reserves                   | Save and continue         |
| **Annuity comparison**         | Product structure, income timing, guarantees and conditions, costs, withdrawal restrictions               | Review product details    |
| **Replacement analysis**       | Existing versus proposed contract, charges, benefits retained or lost, unresolved questions               | Request specialist review |
| **Illustration review**        | Carrier-provided scenarios, assumptions, dates, guaranteed and nonguaranteed values clearly distinguished | Review illustration       |
| **Contract service dashboard** | Confirmed contract status, documents, payment schedule, service requests, review dates                    | View contract             |

**Evaluation of your current page**

The active intake has eight annuity-specific sections covering consumer context, income goals, finances, existing contracts, product preferences, risk, disclosures, and certification. It captures replacement intent and liquidity needs explicitly—both deserve prominent placement in the review screen. [Source: Xenhey Annuities](https://www.xenhey.com/api/store/4D2A41AE60A643EF96547DD3C81DDAF4)

| Area                  | Finding in the source                                                                                                                         | Recommended edit                                                                             |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------- |
| Dashboard accuracy    | Consumer metrics are fixed, including “Annuity types: 4,” while the comparison defines five types.                                            | Calculate counts from the catalog and progress from the selected case.                       |
| Replacement questions | Existing-contract details and a replacement acknowledgment appear for everyone.                                                               | Show detailed replacement questions when the answer is Yes, Possible, or Not sure.           |
| Multiple contracts    | “Multiple contracts” is available, but subsequent fields describe only one existing contract.                                                 | Add a repeatable contract summary with a separate review status for each.                    |
| Ownership context     | Individual, Joint, and Trust are supported, but the active intake does not distinguish owner, annuitant, and authorized representative roles. | Add role and authority questions; route identifying documents through the secure process.    |
| Draft saving          | “Save draft” uses full required-field validation.                                                                                             | Allow incomplete drafts; validate completeness when submitting.                              |
| Editing cases         | The form is populated without first resetting prior values; checkbox hydration uses `Boolean(value)`.                                         | Reset before loading and normalize stored booleans explicitly.                               |
| Table updates         | Submission saves local JSON without updating the cases collection or refreshing its table.                                                    | Persist by case ID, then update the matching row and dashboard.                              |
| Comparison navigation | Every “Review costs” link uses the same destination without identifying the selected type.                                                    | Carry the case and product-type identifiers into the cost screen.                            |
| Disclosure tracking   | Several required checkboxes say “I will review.”                                                                                              | Separate planned review from documents delivered, acknowledged, and requiring clarification. |
| Reused code           | An older investment-products `steps` array remains alongside the active `annuitySteps`.                                                       | Remove unused definitions after checking references to reduce maintenance confusion.         |

These findings come from the code embedded in your [provided page](https://www.xenhey.com/api/store/4D2A41AE60A643EF96547DD3C81DDAF4).

**Recommended comparison layout**

Let users select two or three products and compare the same fields side by side:

| Comparison group | Fields to display                                                          |
| ---------------- | -------------------------------------------------------------------------- |
| Product identity | Issuing insurer, product name, contract/form reference, proposal date      |
| Income           | Proposed start date, frequency, payout option, applicable conditions       |
| Access to money  | Surrender schedule, withdrawal provisions, applicable adjustments          |
| Costs            | Contract charges, optional rider charges, other applicable expenses        |
| Guarantees       | What is guaranteed, by whom, conditions, and supporting contract reference |
| Illustrations    | Assumptions, scenario labels, source document, preparation date            |
| Replacement      | Existing benefits, proposed changes, estimated charges, review outcome     |

Use **Not provided** for missing information. Keep consumer preferences, carrier illustrations, and confirmed contract terms visibly distinct.

**Codex steps to populate the table from intake edits**

| Step | Implementation task                                                                                                   | Acceptance check                                               |
| ---- | --------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| 1    | Define one case model with stable ID, consumer profile, existing-contract summaries, workflow status, and timestamps. | Intake and dashboard reference the same case.                  |
| 2    | Separate draft saving from final validation.                                                                          | A partially completed profile saves and reloads.               |
| 3    | Reset and hydrate the selected case, including repeated contract entries.                                             | Switching cases retains no previous consumer’s answers.        |
| 4    | Add conditional questions for ownership, replacement, and product interests.                                          | Only applicable questions block submission.                    |
| 5    | Save edits under the existing case ID.                                                                                | Repeated saves update one case without duplicates.             |
| 6    | Map answers to consumer name, consumer type, annuity interest, income horizon, replacement intent, and updated date.  | Saved changes appear in the corresponding table row.           |
| 7    | Derive progress and review tasks from actual case events.                                                             | Saving an intake does not imply approval or contract issuance. |
| 8    | Verify draft recovery, edit/save/reload, multiple contracts, and failed saves.                                        | Answers remain intact and status messages reflect the outcome. |

Prioritize **working drafts and case updates**, followed by **replacement comparisons and document-based illustration review**.
