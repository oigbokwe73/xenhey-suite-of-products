Your [Xenhey Payroll Services page](https://www.xenhey.com/api/store/8A08E2B8FA0D4B3A89D44F27CF7441DC) opens an **Employer Dashboard**. It has broad onboarding and operations coverage; the main improvement is to make running, reviewing and approving payroll a complete workflow.

I reviewed its HTML and JavaScript. I did not submit forms, run payroll or test separately linked pages.

**Payroll UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation or verified current vendor functionality.

![Image](https://images.openai.com/static-rsc-4/qv7ElyEXqilcPvA2emHP7oiFQBPHfNq6cga3o4puM0sD8VUrfL56ZQ3Y5Lk_1pKueAVEL8fuzImCFudPb5EseS3FpQ_2NDMtVyVnEOBdmMlxcMucCeb_R7LBlKEkLeyv-879F-58qzyOXmGcI9o9Ro1fSZVvsAr7InMHC0rRn4vQm4d-75Z2yN8qlj77E6-P?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/b7M1uQpR98kaIo7qVLONEF5oiqlXbAUz4fCkHkJkXXaP8T5RvKrpVg5x17OpU8LDsLBe-J1x8wIQQTq_h6yplSQGR6m6bJeSOja5kZIKO7347nY9AeWGkJvmHltvyU5z6I69k1MeB_SbP5nL2-fa8m7vAmxiOy23fT17-w5FDsl6FsJ2eMf0YCWw6ezmvoA6?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/tv7my2lCvn1Fq-nOa8SRB19wUxcKIfRQxEx9CC8nl2k-Jrnu1eivrpo5DCa3jv-5YBpmW8QWJpvILzohLQLxdpNGBpTMAb48Yrg0HoAR4aV_5zXm8YeiASHb2BhzFjMzhkEsI6324unbnYd02ix6UxYngF6TRwe-SB8pmgV1hbdmeuHIh-Sr1r8CxjHmrAgi?purpose=fullsize)

| Screen                | What users should see                                                      | Primary actions                   |
| --------------------- | -------------------------------------------------------------------------- | --------------------------------- |
| Employer dashboard    | Next payday, submission deadline, payroll status and unresolved exceptions | Continue payroll, resolve issues  |
| Company onboarding    | Setup checklist, tax registrations, workers, funding and authorizations    | Continue setup, save draft        |
| Employee directory    | Worker, department, classification, pay type and setup status              | Add employee, import, edit        |
| Time and attendance   | Hours, leave, overtime and manager approvals                               | Review, correct, approve          |
| Run payroll           | Employee earnings, adjustments and calculated totals                       | Enter changes, calculate, preview |
| Payroll approval      | Gross pay, net pay, taxes, funding requirement and exceptions              | Review, approve, return           |
| Payroll history       | Pay periods, payment dates, totals and processing status                   | View register, download reports   |
| Employee self-service | Pay statements, tax documents and profile information                      | View payslip, request changes     |
| Tax operations        | Deposits, filings, deadlines, confirmations and exceptions                 | Review status, resolve issue      |

**Evaluation of your current implementation**

Your source defines an eleven-step onboarding wizard covering company information, jurisdictions, schedules, workers, earnings, deductions, benefits, payments, prior balances, documents and authorization. It also defines operations screens for processing, exceptions, filings, amendments and year-end work. [Source: Xenhey Payroll Services](https://www.xenhey.com/api/store/8A08E2B8FA0D4B3A89D44F27CF7441DC).

| Finding                                                                                     | Recommendation                                                                        |
| ------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Employer dashboard uses fixed figures: 42 employees, $48,620 draft gross and two exceptions | Calculate these from the selected company and payroll run                             |
| “Next payroll” is hard-coded to September 11                                                | Use the configured payroll calendar; distinguish upcoming, overdue and completed runs |
| Onboarding progress remains visible alongside operational payroll                           | Show setup progress before go-live and payroll activity after activation              |
| Run Payroll is a generic aggregate-input form                                               | Add an employee-level earnings grid and calculated preview                            |
| Approval is another generic form                                                            | Display a read-only calculation snapshot with explicit approval actions               |
| Employee and time tables reuse company-level payroll sample rows                            | Supply datasets and columns specific to employees and time entries                    |
| Wizard navigation redraws fields without preserving current input                           | Save each section before navigation and restore it when revisited                     |
| Main Save Draft stores only step and timestamp                                              | Persist all onboarding sections under a stable company/intake ID                      |
| Step submissions overwrite the same form key                                                | Merge section updates instead of replacing previous sections                          |
| Final onboarding submission only logs a fixed sample ID and displays a toast                | Validate the full intake and confirm backend persistence before reporting success     |

**1. Employer dashboard**

Make the next required action prominent. A useful dashboard would contain:

| Area            | Example content                                                    |
| --------------- | ------------------------------------------------------------------ |
| Next payroll    | Pay period, payday and submission cutoff with timezone             |
| Readiness       | Approved timecards, missing worker setup and unresolved exceptions |
| Cost preview    | Gross wages, employer costs and total funding requirement          |
| Approvals       | Draft, awaiting approval, approved or submitted                    |
| Recent activity | Last payroll, returned payments and completed reports              |
| Quick actions   | Run payroll, add employee, approve time, view reports              |

Use actual processing states. “Submitted” should not imply that employees have been paid.

**2. Company onboarding**

Keep your existing eleven sections, but improve how they behave:

* Show completion and validation status for each section.
* Provide one clear **Save and exit** action.
* Restore saved values after navigation or refresh.
* Make questions conditional on company configuration.
* Add an import preview for workers and prior balances, including row-level errors.
* Show a final review summary with **Edit section** links.
* Keep parallel-test results and go-live readiness visible.

Payment-provider tokens and electronic-signature evidence should be supplied through secure integrations, rather than typed into ordinary intake fields.

**3. Run Payroll screen**

Use an editable earnings grid. The following records are synthetic:

| Employee    | Pay type | Regular hours | Overtime hours | Bonus | Reimbursement | Review status         |
| ----------- | -------- | ------------: | -------------: | ----: | ------------: | --------------------- |
| Alex Morgan | Hourly   |            80 |              4 |    $0 |           $45 | Review overtime       |
| Jamie Lee   | Salary   |             — |              — |  $250 |            $0 | Ready                 |
| Taylor Reed | Hourly   |            72 |              0 |    $0 |            $0 | Missing time approval |

Above the grid, display company, pay group, pay period and payday.

Recommended controls:

* Import approved time
* Add earning or adjustment
* Compare with previous payroll
* Filter employees with exceptions
* Save draft
* Calculate and preview

Tax, overtime and deduction calculations should come from the configured payroll engine. The UI should display the results and explain exceptions.

**4. Payroll review and approval**

Provide a summary that makes both employee payments and employer funding clear.

| Review section | Information                                                    |
| -------------- | -------------------------------------------------------------- |
| Employee pay   | Gross wages, deductions, employee taxes and net pay            |
| Employer costs | Employer taxes, contributions and service fees                 |
| Funding        | Required debit, masked funding source and scheduled debit date |
| Delivery       | Direct-deposit total, check total and payday                   |
| Comparison     | Changes from the previous run                                  |
| Exceptions     | Blocking issues, warnings and resolutions                      |

Use **Return for correction** and **Approve payroll** actions. If payroll data changes after approval, require review of the updated calculation before submission.

**5. Employee self-service**

Your bundled self-service screen is currently a status-oriented form. Replace it with a personal employee workspace:

* Latest payslip and payment date
* Pay-statement history
* Year-to-date earnings
* Tax-document availability
* Profile and contact details
* Masked direct-deposit information
* Requests to update payment or tax information
* Support messages

Scope each employee’s access to their own records. Use synthetic information for the browser-storage prototype.

**6. Payroll operations dashboard**

Organize the administrator experience around work requiring attention:

| Queue              | Useful columns                                                    |
| ------------------ | ----------------------------------------------------------------- |
| Implementations    | Company, setup stage, missing items, owner, target go-live        |
| Payroll processing | Company, pay period, payday, cutoff, status, funding total        |
| Exceptions         | Run, employee reference, issue, severity, owner, resolution       |
| Payment operations | Run, debit status, deposit status, returned items                 |
| Tax filings        | Company, authority, period, deadline, status, confirmation        |
| Agency notices     | Company, notice reference, response deadline, assigned specialist |

For Xenhey, prioritize **reliable onboarding persistence**, then the **employee-level payroll grid**, **calculated approval preview**, and **processing-status tracking**. Those changes will make the existing navigation support a usable payroll workflow.
