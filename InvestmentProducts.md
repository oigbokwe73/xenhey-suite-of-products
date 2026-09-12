Your [Investment Products page](https://www.xenhey.com/api/store/A7E28C42DC3E42FDB448392DDFA04FB4) provides a useful **investor discovery and review workspace**. My recommendation is to emphasize profile completion, product education, and the next review action, then connect saved intake changes directly to the dashboard.

I reviewed the HTML and embedded JavaScript. I did not submit information or test linked pages, account opening, or investment transactions.

**Investment Products UI examples**

These images are design inspiration, not screenshots of your Xenhey page or verified provider functionality.

![Image](https://images.openai.com/static-rsc-4/IABQPWL4_XOiPXqYrJ4b2ml67KhfiCjny41fS84TcDMTjuRUar0gsZ93yHX9cUrCElOg0c90z3yLY6QbpxxrWvAstu2JdCwEvHJN96n1t_wFCtwM_glXm9GqjYb-9wAEUjkA7TauE_-S5SzYfXuUrmJ60zw6Wf50ScgOakhdwA4cUpktAI5o0z7yOK98nUUH?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/SqWCa74OGBc4fCMG8Q1EIz2q5RAyP2RthJYMbdAfUUaJ8bfjK_W9TZq7IFyCQ0X9n4FXOyM2hJ6oim1kKMBDGJM848ATyF8rIp7SLfpctF0gV-VZ75JifVEYkAQmO1ATb17yzPhqtnNRgU_aHtee7vHWzMkitDX-D3x8Cwn6Ts_kcnbPhHJguLCQ4nGvWqHm?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Tubz5rZySjG892qiAB3r0jshKAo6krGcqFs84kg_PCDVVucBY5dERdFLQKrL1YE6jNrogmWhyy34o_T_WIjLJMGcRZOI4bCDYZNLSZoPyX2oVq62VbWSM5Yr4v7mI4zv3JmMc09xI8a6rBMpN39zM-yF6BVigrkdGq4p48oW0DqQtZPAK-tSYEVL3fs-0QiS?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/MBFLTQKRiGsllI78c9fuApNiePCbET-x5VDC0CutRobMUob6Y7C9FRp7wGduAI6GpWmqc6taPWd-5Q08dK9-7pLPOnuX-eyngBcqTYW_ZznTKeIhDxO86FxmE9fBY6DJRxDDr-UNOCy4S9S9SdDBVeqq8l1cfV-Y48_dHml-LIs46CtWhzuYST1MhXlfUU95?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/ZcuQ70_r2BdwqJUm7UGr6D4DcSo_Y_7TU8wTZxnbkJjQyvETgsuBg-WIjLDWOLUNUrqukJBymLlSNBK-O6UVslxC3jRd4EgSU49BIO8-BtQiApqArhLHF86UI_7MKt-nFDRlAv-SW5j8BEJFvjxEidz59MC_OZmj5Rh0zvuD5VlR7bmCfKlpHPoDp7dtYqoY?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/pZxXLKiW6F4Izeh1A0Wsg-yzRitnBsyYQKkMuNyBSs1WalIlKzkarbr0dmnzGVIWGAR9Fkj3xkx_nrXjbjsf1epnCceaBkXjOwdWLcsg8JeOvLkP-8__Noyr9CVAILZO_RiwpMz4lMPEj-xfpSn_9678j_KYfFreiNGge5V_wmIu04qGa6RXQPtEi8HN4wBP?purpose=fullsize)

| UI example                         | Recommended content                                                                              | Primary action     |
| ---------------------------------- | ------------------------------------------------------------------------------------------------ | ------------------ |
| **Investor dashboard**             | Profile progress, outstanding questions, assigned reviewer, next appointment, application status | Continue profile   |
| **Goal-based intake**              | Investment purpose, amount range, time horizon, income needs, liquidity needs                    | Save and continue  |
| **Risk-profile review**            | Self-described tolerance, loss capacity, experience, answers needing clarification               | Review answers     |
| **Product explorer**               | Category, purpose, risks, liquidity, costs, supporting disclosures                               | Compare categories |
| **Account and service comparison** | Account ownership, brokerage/advisory relationship, services, fees, responsibilities             | Request discussion |
| **Application tracker**            | Profile review, required documents, disclosures, provider decision, funding status               | Complete next task |

For a later connected-account experience, add holdings, transactions, allocation, and performance—with data timestamps and clearly explained calculations.

**Evaluation of your current page**

The embedded intake contains eight sections covering investor context, goals, finances, experience, risk, account preferences, products/disclosures, and security/certification. It also separates **risk tolerance** from **financial ability to absorb loss**, which is worth retaining. [Source: Xenhey Investment Products](https://www.xenhey.com/api/store/A7E28C42DC3E42FDB448392DDFA04FB4)

| Area                        | Finding in the source                                                                                                                                                  | Recommended edit                                                                                              |
| --------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Dashboard accuracy          | Stage, profile sections, product categories, and next-review interval are hard-coded. The dashboard says six categories, while the product explorer defines five rows. | Derive metrics from case records and a shared category catalog.                                               |
| Risk labeling               | The cases table labels the self-reported `riskTolerance` value “Risk profile.”                                                                                         | Rename it **Self-reported tolerance**; display reviewer status separately.                                    |
| Investor-specific questions | Individuals, trusts, and businesses receive the same age, employment, and financial questions.                                                                         | Branch by investor type and distinguish the investor/entity from its authorized contact.                      |
| Product selections          | “Products previously used” and “Product categories to discuss” are single-select fields.                                                                               | Allow multiple selections, with experience captured per category.                                             |
| Draft saving                | Saving a draft invokes full required-field validation.                                                                                                                 | Save incomplete drafts and validate completeness at submission.                                               |
| Editing cases               | The edit handler loads supplied fields without resetting the previous form; checkbox values use `Boolean(value)`.                                                      | Reset first and normalize stored types so `"false"` does not become checked.                                  |
| Table updates               | Submission saves local JSON but does not update the cases collection or redraw its table.                                                                              | Persist by case ID, then refresh the corresponding row and metrics.                                           |
| Product comparison          | Every “Review costs” link uses the same destination without a selected category identifier.                                                                            | Carry the case and category into the comparison screen.                                                       |
| Disclosure acknowledgments  | Several checkboxes say “I will review” documents.                                                                                                                      | Track an intention to review separately from document delivery and acknowledgment.                            |
| Customer language           | Readiness and generic forms expose “JSON” in buttons and messages.                                                                                                     | Use **Save profile**, **Save changes**, and **Submitted for review** after the corresponding action succeeds. |

These findings are based on the code in your [provided page](https://www.xenhey.com/api/store/A7E28C42DC3E42FDB448392DDFA04FB4).

**Recommended intake experience**

| Section                 | Recommended enhancement                                                                                                                                          |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Goals                   | Let users add multiple goals, each with its own horizon, amount range, and liquidity need.                                                                       |
| Financial circumstances | Explain financial terms beside inputs; offer “Needs discussion” where an applicant cannot answer accurately.                                                     |
| Experience              | Use a repeatable table: product category, experience level, years used, and frequency.                                                                           |
| Risk and loss capacity  | Flag conflicting answers for clarification, such as aggressive tolerance combined with very limited loss capacity. Do not silently replace answers with a score. |
| Service preferences     | Keep account type, service relationship, and management preference as separate decisions.                                                                        |
| Product education       | Separate options, margin, and alternative investments into distinct entries; the current explorer combines them.                                                 |
| Final review            | Show editable answers, unresolved questions, disclosure status, and the next review step.                                                                        |

**Codex steps to populate the table from intake edits**

| Step | Implementation task                                                                                         | Acceptance check                                                                     |
| ---- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| 1    | Define a shared case model with stable ID, profile answers, workflow status, timestamps, and version.       | Form and table reference the same case.                                              |
| 2    | Separate draft serialization from submission validation.                                                    | An incomplete profile saves and reloads.                                             |
| 3    | Reset and hydrate the selected case; handle multiselect values and booleans explicitly.                     | Switching cases leaves no previous investor’s answers.                               |
| 4    | Add conditional fields for individual, joint, trust, and business profiles.                                 | Only applicable questions block submission.                                          |
| 5    | Save edits using the existing case ID and retain input on failure.                                          | Repeated saves update one record without duplicates.                                 |
| 6    | Map saved answers to investor name, investor type, objective, horizon, tolerance, status, and updated date. | The edited row reflects the saved profile.                                           |
| 7    | Derive dashboard progress and next actions from case events.                                                | Saving a profile does not automatically imply review completion or account approval. |
| 8    | Verify edit/save/reload, partial drafts, conflicting answers, and failed saves.                             | The workflow preserves answers and reports status accurately.                        |

Prioritize **reliable intake editing, accurate dashboard states, and useful product comparisons** before adding portfolio analytics.
