Your [Xenhey Mortgage Referrals page](https://www.xenhey.com/api/store/8C1DC466B5AF47E0B80F1A48FB28D39E) opens a **Mortgage & Refinancing Referrals dashboard**. Its strongest design direction is a guided journey from **purchase/refinance goals → provider selection → sharing consent → confirmed introduction → follow-up**.

I reviewed the page’s HTML and JavaScript. I did not submit referrals, contact providers or test separately linked pages.

**Mortgage Referral UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/p7BUdEZVt8QsOITB4j_wsd0aHUbXLqPNbbwyjDxq__drmPVi90qAsCmI93dx34uBQstJn5pUb4ZG9oVpy01CoTPjFs-HG8zJJHZ0w3ggARpis2ZW4g8Cbth4gGoXjUl88qCp7r8h6UhFsdngQoEBk0UTVNQxgMPSUMeK3RejsJ_lk4_fhfFg5Al_8uenpRP1?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/wETsWu_6RXpxzNy3Wp-sYrug4qaSZRbBz3d5ZJ5FgSz9ysHCtRvgK8FmaVuRYOEv-1UlhclMuc4WooEZMHjs5kK3wii7Pd_ZSkUpZs63d1kyfuslGBw5Nl-7nXn_h1J2EB17OkIKgd8MvqsOZzhjcBCJITJ70_jhlgBngsE2E3K-KcD_V7QzWL9HWsjsT33V?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/INEBADvEdwJ_iZ65zbg59-jWuIsA6FPPMxrGFf7ZLTySGydNNxaRlEjPbbPXDjg2Ng6s1mhpEqjyVZIW2pHcRQASxOJNTv8t9TysQC2lySMtbSf8yGwsalLAcKwEcfrmUO5SO3tSI6bNnu4zHC05-QDj1d86C6rrXMYCcRFhqmCx5i_OSg415HvulGUZcHlL?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/UGsRIX98xzTZFALCVjVmSiThuXemLkA7Ncb-tV_uaMp9oXg3omg0cCHJYEiK8GBi-_6TZkmZ-HRHTgRHq_cfb16KZgQo-3wx5Neb4qVgNIUspwHI4biauTq2oBTTcJNWtkc5c-Kf4aSVMl2hKLwOMhGf_Gld7owNehnYlJ50t1J10Nzcyp63pGwem19ukTOw?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/eNIugsuRZ6bBFw32tjGAAKFohxHxRZkzhooNA9WpRMB3PGp8gCDT0iVQxT2TE0S1-zyFl_qtfgrkcz8PQKI-5WZwmwDE_4_Y6Iy584QBdoM1mzE0YRpeSqfuwgUWyLYfAnXSEgsLPqieWgdMtLfFkg_UGySc6wmSZrQqjZiRvldzwzYGBYfemh63nrcOXtgj?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/JfD-CaKz1sQUC_hXBi8yoXCUf9tddTmszbGhbvMeZc0yx7yJF8BdrEaeJkj2ZBJJ8hwWWahn0fkXcSghnYMaiYVm7JwenenR1xJE1MWZGNCTJbBwy7942Tp2QvPdGQF5aFEeM9BQaxBs4jo7TVdTw6-ICXgufr8ZKP0Kb2p9SA6D-vx3D8T9Xbl6DUCRzR_J?purpose=fullsize)

| Screen                    | What users should see                                                 | Main actions                     |
| ------------------------- | --------------------------------------------------------------------- | -------------------------------- |
| Customer dashboard        | Selected referral, goals, provider, next action and appointments      | Continue, view referral          |
| Purchase/refinance intake | Property summary, financing goals, timeline and contact preferences   | Save draft, review               |
| Provider comparison       | State coverage, services, contact options and verification references | Compare, choose                  |
| Sharing consent           | Selected recipient, information shared and purpose                    | Review, authorize                |
| Referral tracking         | Delivery, provider response, contact attempts and next steps          | View history, request help       |
| Appointment               | Provider, available time, timezone and confirmation                   | Schedule, reschedule             |
| Document readiness        | Checklist and secure provider handoff                                 | Mark ready, open provider portal |
| Loan Estimate tracker     | Provider-issued estimates and comparison fields                       | Record receipt, compare          |
| Referral management       | Contact preferences, withdrawal and closure status                    | Update preferences, withdraw     |

**Evaluation of your current implementation**

The source already makes the referral-only purpose clear. It includes a seven-section intake, provider comparison, consent, appointments, document readiness and Loan Estimate tracking. Providers are explicitly presented as demonstrations with `NMLS-DEMO` references. [Source: Xenhey Mortgage Referrals](https://www.xenhey.com/api/store/8C1DC466B5AF47E0B80F1A48FB28D39E).

| Finding                                                                                                      | Recommended improvement                                               |
| ------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------- |
| Customer metrics are fixed: 18 active referrals, four ready to share, seven responses and three appointments | Calculate metrics for the authenticated customer                      |
| Dashboard displays a slice of the general referral collection                                                | Enforce customer-scoped records on the backend                        |
| Intake sections remain in one form and are hidden when inactive                                              | Preserve this approach; it retains entered values during step changes |
| Save Draft runs full required-field validation                                                               | Allow incomplete drafts                                               |
| Submission saves a separate browser-storage object                                                           | Update the referral collection and refresh its table row              |
| Table uses `applicantName` and `purpose`; intake uses first/last name and `loanPurpose`                      | Map the fields explicitly                                             |
| Every provider’s Choose link opens the same URL without identifying the provider                             | Carry `providerId` into the consent screen                            |
| Referral-status milestones are hard-coded                                                                    | Populate them from confirmed events                                   |
| Appointment form only saves locally                                                                          | Separate a requested appointment from a provider-confirmed booking    |
| Loan Estimate comparison is mostly a tracking form                                                           | Add a structured, source-backed comparison view                       |

**1. Customer dashboard**

For a consumer, prioritize their goal and next action over a large operational table.

Recommended cards:

* **Your goal:** purchase, rate-and-term refinance or cash-out refinance
* **Property:** city, state, property type and intended occupancy
* **Selected provider:** contact and referral status
* **Next step:** review consent, schedule a conversation or respond to a request
* **Upcoming appointment:** date, time and timezone
* **Recent updates:** source and timestamp

Keep multiple referrals accessible through a selector or compact list. “Provider accepted” should describe acceptance of the introduction—not mortgage approval.

**2. Purchase and refinance intake**

Keep your seven sections, with conditional questions:

| Customer goal           | Emphasize                                                                         |
| ----------------------- | --------------------------------------------------------------------------------- |
| Purchase                | Location, property type, purchase timeline, price estimate and down-payment range |
| Rate-and-term refinance | Current balance, rate range, remaining term and intended outcome                  |
| Cash-out refinance      | Current mortgage, estimated property value, desired proceeds and purpose          |

Hide current-mortgage questions for customers buying without an existing mortgage to refinance.

Add a final summary with **Edit section** links. Retain the current use of ranges and readiness information, with formal verification handled through the selected provider.

**3. Provider comparison**

Use comparison cards or a table with specific, inspectable attributes:

| Attribute         | UI treatment                                         |
| ----------------- | ---------------------------------------------------- |
| Provider identity | Company and relevant professional                    |
| State coverage    | Coverage for the selected property state             |
| Services          | Purchase, refinance and supported product categories |
| Verification      | Reference, verification date and status              |
| Contact           | Available channels and appointment options           |
| Selection         | Clear explanation of why the provider appears        |
| Action            | View profile, choose provider                        |

Keep demo providers visibly labeled. Replace their data with verified records before offering real introductions.

The selected provider should remain visible throughout consent and submission; changing it should trigger review of the updated sharing authorization.

**4. Consent and lender handoff**

Present a concrete sharing summary:

* Who will receive the referral
* Which contact and referral fields will be shared
* Why the information is being shared
* Preferred contact channel
* Relevant notices and their versions

Use **Review referral** followed by **Authorize and send referral** only when actual delivery is implemented.

Track these separately:

| State                 | Meaning                                             |
| --------------------- | --------------------------------------------------- |
| Draft                 | Information is being prepared                       |
| Consent pending       | Sharing authorization is incomplete                 |
| Ready to send         | Required information and authorization are recorded |
| Sent                  | Delivery has been confirmed                         |
| Provider responded    | Acceptance or another response was received         |
| Appointment confirmed | The meeting was accepted                            |
| Withdrawn/closed      | The referral is no longer progressing               |

A local JSON save must not move the record to **Sent**.

**5. Loan Estimate tracking**

Preserve the distinction between tracking lender documents and issuing loan terms.

For estimates actually received, provide:

* Provider and document date
* Loan amount, type and term
* Interest rate and rate-lock status
* Principal-and-interest payment
* Estimated total monthly payment
* Closing costs
* Estimated cash to close
* Source-document reference

Show missing values as unknown. Highlight differences in loan amount, term, dates and assumptions before presenting comparisons. Do not generate approval or savings claims from referral inputs alone.

**6. Referral-operations workspace**

Organize staff queues around:

* Consent awaiting completion
* Referrals ready for authorized delivery
* Delivery failures
* Provider responses pending
* Contact follow-ups
* Appointment requests
* Withdrawals and complaints

Each item should have a referral ID, selected provider, owner, last event and next action. Keep review controls separate from customer-editable statuses.

For Xenhey, prioritize **customer-specific records → complete draft saving → selected-provider handoff → explicit sharing review → confirmed referral events → appointment and estimate tracking**.
