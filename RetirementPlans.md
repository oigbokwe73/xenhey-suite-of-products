Your [Retirement Plans page](https://www.xenhey.com/api/store/B9C44D88A2734456A46D56732D92DF01) is structured as an **employer plan-sponsor workspace**. I recommend centering the experience on plan selection, provider comparison, and implementation progress.

I reviewed its HTML and JavaScript, including the embedded intake definitions. I did not submit information or test linked pages and integrations.

**Retirement Plans UI examples**

These images are visual inspiration, not screenshots of your Xenhey implementation or verified provider functionality.

![Image](https://images.openai.com/static-rsc-4/8zyUQPDY1Bz704GdiV34huuY6Lib9l89t1x_LOVWFTJu6GqNgaPq7ekoMNnaNAL4xjreGw7dL1qRhBhXsT8i-dS9vX3CM0TIlZKW-8-U2mgk4uKfLQ3I7GozOWSygDe5zbYbN2VwD1Aofs-8aKjGLpi-9rVup1aAXB-beYyQzCao-oZI3b8AdUlG5HX7YZgq?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/LuNgCVLPGqxiTaTip5k6obZDG9xihHzTtlyk8LeOcxIGsK1mtkXGNDZvByyXLLeywoHTmgYCryprXfKx82rJ1gEoXA2Gzd_5GhNlQNojzPhAA_uEVChAa4EnRsctQ3Bn2hH0Bj9gKaHYl07OwgJ0s9Qf7yhjP1IdfG79vMpduNwa2ducSn7A4qTPPl-k5lxz?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/59tOWEljVxz8WgDbP6fDgaOqvfTeTo3kmEAieWuB3gPmKcHp_tNSi4wDhukjpQ0TdSMryr5RtSx7Gvq4NjaP9mgVEF9JwUlJEi-_9VhY6HHhtd2NbZMX8PzwpzkA7ofFIBoz6zWYJH-on-zwzRbhr0TFqdd_qtZlBDaNm_-epnlTUfxWaK3X_H--INSLrd8l?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/EZrQCNdoMZtQC7LAtSUwAEs2wvy1KO3W-yusIQH-gcWLHCPvHbHq78JaPRLD3fg6x2YFvmqkYOzEq8Gb8vgMDAbrm8wVZSEomUvhkkm3vvaaChPgTv1lhxSz39mORUV7NemtK_aq2G1MQDzHEVJxoOn1jKHi-J86kq5qbGN-j8xsSdlaoU0Hcylwyp7u0ehy?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/ntBN-NKgOnb2LS7ar315MMJiX-MbgMwPIfVSL6M_6oDhui01HJsZbmaybDDI-L3tQBRqT1lKhK18P7gvd0CAvJ9rjYOjtbMx0DwwLc7E-w2rVioAtHCFdQ0hztHaPYAkB7lIykovpfTz9ScoSLF24Uh-IhOQX7w-A2vnIetQ4n-WujuspmbGzRg0Q5dqaSp8?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/PPS-Je8HMSDftf6FSTrtw3mo5IX7OfUgnwBGFcIGN4I4uAZiVUUohAiVQEAemuL0yuD0BrIbjWWZDeh8kZnw8-NJuKyvJ3lNTM7_0tlAACkFUeL-fn9TKh9RSxBsTCGF0NfWNl3e2MIFjatgVMeJ7JiacDlBSFG6NY0PpUyGm28E0pI5sA3BDIvY3YdAkJNv?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/jlqMS6j_dbBO6-e7tAIwlLlPEuJ_x7jZ8Svo5Dybc-krmf1jWWz-qJn3pRPIA2em_-ak2xyljvSZYbMAtojL_enPjS2pantQckRU4mz_Z4NO1r5GtWBPFu_13YYh-MLu-1CSq62UuAU9vuRbDoGiG5qarTfWAh1JUP0lj3ojbIWUF-fxjPUkJMIHhO65muOP?purpose=fullsize)

| UI example                      | Recommended screen content                                                                  | Main action              |
| ------------------------------- | ------------------------------------------------------------------------------------------- | ------------------------ |
| **Sponsor dashboard**           | Current stage, outstanding decisions, assigned specialist, next milestone, target launch    | Continue setup           |
| **Plan discovery wizard**       | Employer profile, workforce, current arrangement, goals, plan preferences                   | Save and continue        |
| **Plan comparison**             | Plan options, relevant features, administrative responsibilities, unresolved questions      | Request plan review      |
| **Provider and fee comparison** | Services, payroll compatibility, fee components, responsibilities, proposal dates           | Review proposal          |
| **Implementation tracker**      | Documents, payroll setup, enrollment preparation, owners, dependencies, completion evidence | Complete next task       |
| **Ongoing administration**      | Contribution exceptions, service requests, review tasks, documents, scheduled activities    | Resolve outstanding item |

**Evaluation of your page**

Your embedded intake has eight sections: employer/contact; ownership/current arrangement; plan type/timing; eligibility/vesting; contributions/features; payroll/provider/fees; investments/communications/security; and acknowledgments. This gives the application a useful discovery foundation. [Source: Xenhey Retirement Plans](https://www.xenhey.com/api/store/B9C44D88A2734456A46D56732D92DF01)

| Area                     | Finding in the source                                                                                                           | Recommended edit                                                                                                        |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| Dashboard                | Stage, items reviewed, providers compared, and launch window are fixed values.                                                  | Derive these from the selected employer’s case. Label demonstration metrics clearly.                                    |
| Plan-specific questions  | The same eligibility, vesting, and contribution fields appear regardless of selected plan type.                                 | Add conditional questions and plan-specific professional-review flags. Treat selections as proposed design preferences. |
| Draft saving             | “Save draft” calls the same required-field validation as submission.                                                            | Permit incomplete drafts; enforce completeness when submitting.                                                         |
| Form navigation          | All sections remain in one form, preserving values while switching steps.                                                       | Add Back/Next controls, section completion, and navigation to the first invalid field.                                  |
| Editing records          | The edit handler populates supplied fields without first resetting the form.                                                    | Clear the previous case before loading another to prevent retained answers.                                             |
| Checkbox hydration       | Stored values are converted with `Boolean(value)`.                                                                              | Normalize types explicitly; the string `"false"` otherwise becomes checked.                                             |
| Saving table edits       | Submission writes browser-local JSON without updating the cases collection or refreshing its table.                             | Save by case ID and update the corresponding table row after successful persistence.                                    |
| Provider comparison      | Four providers are explicitly synthetic; all “Review fees” links share a destination without identifying the selected provider. | Carry case and provider identifiers into a detailed proposal comparison.                                                |
| Customer-facing language | Buttons and notifications expose “JSON” terminology.                                                                            | Use **Submit for plan review**, **Save changes**, and **Draft saved**.                                                  |
| Implementation timeline  | Milestones and current stage are hard-coded.                                                                                    | Track task owner, due date, dependencies, and actual completion per case.                                               |

These are source-level findings from the [provided Retirement Plans page](https://www.xenhey.com/api/store/B9C44D88A2734456A46D56732D92DF01).

**Recommended intake improvements**

Keep the existing sections, with these additions:

| Intake section                | Suggested enhancement                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Employer and workforce        | Add “Owner-only / No non-owner employees” and “Unknown” where appropriate; clarify total versus estimated eligible employees.  |
| Current arrangement           | Branch between new-plan setup and existing-plan conversion; show current-provider and transition questions only when relevant. |
| Plan selection                | Preserve “Not sure” and explain unfamiliar terms beside the field.                                                             |
| Eligibility and contributions | Show applicable questions based on the proposed plan; distinguish employer preferences from reviewed plan provisions.          |
| Provider and fees             | Capture payroll compatibility, services requested, fee payer, and proposal reference.                                          |
| Final review                  | Present an editable summary, unresolved questions, and acknowledgment status before submission.                                |

For provider comparisons, use consistent columns for setup costs, recurring employer charges, per-participant charges, asset-based charges, included services, and assumptions. Display **Not provided** for missing costs instead of treating them as zero.

**Codex steps to populate the table from intake edits**

| Step | Implementation task                                                                                        | Acceptance check                                                   |
| ---- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| 1    | Define one case model with `id`, `formData`, `status`, `updatedAt`, and version.                           | Intake and dashboard reference the same case.                      |
| 2    | Separate draft saving from submission validation.                                                          | Partially completed discovery can be saved and restored.           |
| 3    | Reset and hydrate the form when Edit is selected.                                                          | Switching employers leaves no answers from the previous case.      |
| 4    | Add conditional sections for new plans, conversions, and proposed plan types.                              | Only applicable questions block submission.                        |
| 5    | Persist changes using the existing case ID.                                                                | Saving an edit updates one case without creating a duplicate.      |
| 6    | Map saved answers to table columns: employer, proposed plan type, employee band, status, and updated date. | Changed answers appear immediately after a successful save.        |
| 7    | Recalculate dashboard metrics and implementation progress.                                                 | Counts and milestones reflect saved case records.                  |
| 8    | Verify reload, failed-save handling, and repeated edits.                                                   | Saved changes survive reload; failed saves retain entered answers. |

**First priority:** make the discovery-to-table workflow reliable, then add provider comparison and task-driven implementation tracking.
