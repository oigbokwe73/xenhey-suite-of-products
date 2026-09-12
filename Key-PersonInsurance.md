Your [Xenhey Key-Person Insurance page](https://www.xenhey.com/api/store/BC5AA34282B4490CA8BAACB7A171737E) opens a **Customer Dashboard** for employer-owned life-insurance cases. The strongest improvement is to organize the experience around **the key person, business impact, proposed coverage, consent progress and carrier-confirmed policy status**.

I reviewed its HTML and JavaScript. I did not submit cases or test separately linked pages, carrier feeds or underwriting integrations.

**Key-Person Insurance UI examples**

These images are related insurance and business-protection design references, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/Ag5VswWqa_Gov9CrdKMJmQ9VWPl6Pz8f2JT2gyKu5N1LjZmgg-RSXjwXRSmfrkObxd4-Doz-_cpdywpBhBhlZBctfwEh7KAqYUsorkmpCNtsiQxYrEiAnymj7em6Ulo4BO_qo25iuGKC05lHCx134jALTWc3PkMIBPzF2PV3uRBryngZYmt93SB7KNL9k0NN?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/7wJb_dEOpxfdunZ8fx_VeMb0gdJ50IxRLrrzhJc_2N7A1_xiHLT2VU9RJKnlmjePCByJzofC_u9Yaz0a37KDHj0kdwgouKJLUQnsYKI0oa_4Ldlc7FLrwoQghycHwEb2gTVIQtJBP7Tk9f_i8Aln94wGxBxSfzBDo4UugyhM4q8tTryTWlgyxZd2-Ulzu-QJ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/5N_gLZE_WLdzC_x93gFCQnl8OwFWT7BC48ApbKVRp5w1jdJBKslxoxzcnyYgMnqy7pUBw3IW-vFNICgpgqWzrby8-er4u_F65C3VxiKIJgmXxdH20OUAOBiO-H3YLn4EKPtFZrA8u9ObDVhc8fLsy_rf8eHfyGZOF_2ufQx8BtaTn4etwZ6og0WsPC0pMilN?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/X3jYNLhPYPfTWtOzgizVNM2MVkDWV8XicDkdZvszLZS4XLfdVvQs7_psqLVmB4yka4CzZv6025sq3ln82KRFcpp5toClnvS_MF1gu7Lfh3LnJt4MPLOb1KTX5_Yp3wXH6HbPZC9r19lD1WLL03TEmudu3u78j1jFqY6FiEDC_XXpA4bYViRMcR0Forh6uAv6?purpose=fullsize)

| Screen                        | What users should see                                            | Main actions                   |
| ----------------------------- | ---------------------------------------------------------------- | ------------------------------ |
| Business-protection dashboard | Key people, open cases, requested coverage and outstanding tasks | View case, add key person      |
| Key-person profile            | Role, business dependency, tenure and coverage purpose           | Edit profile                   |
| Business-impact worksheet     | Replacement costs, disruption period and supporting assumptions  | Review assumptions             |
| Coverage comparison           | Face amount, duration, product type, premium and conditions      | Compare, request review        |
| Ownership structure           | Proposed insured, owner, beneficiary and premium payer           | Review structure               |
| Notice and consent            | Readiness, secure document status and verification               | Open secure process, track     |
| Underwriting tracker          | Requirements, responsible party and next action                  | Respond through carrier        |
| Policy management             | Confirmed coverage, premium schedule and review date             | View documents, request change |

**Evaluation of your current implementation**

Your seven-section intake already covers business details, the key person, financial justification, coverage needs, ownership/funding, notice-and-consent readiness, and carrier contact consent. It also includes specialist-review tracking. [Source: Xenhey Key-Person Insurance](https://www.xenhey.com/api/store/BC5AA34282B4490CA8BAACB7A171737E).

| Finding                                                                                    | Recommended improvement                                                             |
| ------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------- |
| Dashboard counts are fixed: six quotes, two key people, two consent records and one policy | Calculate them for the selected business                                            |
| Table labels requested face amount as “Coverage”                                           | Label it **Requested coverage**; show in-force coverage separately                  |
| Table uses `keyPersonName`, while intake captures first and last names                     | Add an explicit mapping                                                             |
| Edit toast references `applicantName` rather than the key-person/business fields           | Display the correct case identity                                                   |
| All intake sections remain in one form                                                     | Preserve this behavior; switching sections retains entered values                   |
| Save Draft requires all required fields                                                    | Allow incomplete drafts                                                             |
| Submission saves a separate browser-storage object                                         | Update the shared case record and refresh its row                                   |
| Carrier Review links omit the selected carrier                                             | Carry the carrier and case identifiers forward                                      |
| Readiness checkboxes can resemble evidence of completed consent                            | Separate readiness, completion and verified evidence                                |
| Generic timeline ends with “Bind”                                                          | Use life-policy stages such as underwriting, offer, issue requirements and in force |
| Source retains unrelated home, renters and auto schemas                                    | Remove or isolate unrelated fields and routes                                       |

**1. Business-protection dashboard**

Use a case list with requested and confirmed coverage clearly separated.

*Illustrative records:*

| Key person  | Business role     | Requested coverage | Case status             | Next action             |
| ----------- | ----------------- | -----------------: | ----------------------- | ----------------------- |
| Alex Morgan | Managing director |         $1,000,000 | Financial review        | Provide justification   |
| Jamie Lee   | Lead engineer     |           $500,000 | Consent process pending | Complete secure process |
| Taylor Reed | Sales director    |         $2,000,000 | Carrier review          | Await response          |

Above the table, show open cases, outstanding tasks, confirmed in-force policies and upcoming reviews. Scope the records to the authenticated business.

**2. Business-impact worksheet**

Expand the existing value bands into a reviewable worksheet:

| Component           | Information to capture                                    |
| ------------------- | --------------------------------------------------------- |
| Role dependency     | Responsibilities, relationships and specialized knowledge |
| Replacement         | Recruiting, interim staffing and training assumptions     |
| Disruption          | Expected duration and operational effects                 |
| Financial impact    | Documented estimates and their sources                    |
| Existing protection | Relevant existing coverage and arrangements               |
| Requested amount    | Customer request and supporting rationale                 |

Show assumptions and potential overlaps. Do not automatically turn the worksheet total into an approved or recommended coverage amount.

**3. Ownership and consent workspace**

Display the proposed arrangement explicitly:

| Party          | Display                                 |
| -------------- | --------------------------------------- |
| Insured person | Selected key person                     |
| Policy owner   | Proposed entity/reference               |
| Beneficiary    | Proposed entity or arrangement          |
| Premium payer  | Proposed payer                          |
| Reviewer       | Assigned producer and relevant advisers |

Your intake allows several ownership and beneficiary arrangements. Route these for appropriate review rather than presenting every combination as interchangeable.

Keep these consent states distinct:

* Not started
* Ready to complete
* Secure process initiated
* Document completed
* Evidence received
* Verified by authorized reviewer

An employer’s readiness checkbox should not stand in for the employee’s completed consent. Employer users should see permitted progress information, while medical answers remain in the carrier’s secure workflow.

**4. Coverage-comparison UI**

Replace a generic selection form with case-specific options.

| Comparison field     | What to display                                                               |
| -------------------- | ----------------------------------------------------------------------------- |
| Product              | Term or permanent product under review                                        |
| Face amount          | Proposed or offered amount                                                    |
| Duration             | Coverage period                                                               |
| Premium              | Payment frequency and guaranteed/non-guaranteed distinctions where applicable |
| Conditions           | Outstanding underwriting or issue requirements                                |
| Supporting documents | Carrier illustration or offer reference and date                              |
| Status               | Indicative, under review, offered or issued                                   |

Avoid ranking options solely by premium. Keep customer preferences separate from carrier offers and confirmed policy details.

**5. Case editing and policy servicing**

Complete the existing Edit workflow by preserving the case ID, saving all sections, updating the key-person name and requested amount, and refreshing the same table row. Reset the form before loading another case to prevent leftover values.

After issuance, prioritize:

* Carrier-confirmed policy status and effective date
* In-force face amount
* Premium schedule
* Owner and beneficiary references
* Annual review date
* Employment or role-change requests
* Secure policy documents

Keep **change requested**, **under review**, and **confirmed** separate.

For Xenhey, prioritize **schema cleanup → accurate case summaries → complete draft saving → consent-evidence tracking → carrier-specific comparisons → policy-review workflows**.
