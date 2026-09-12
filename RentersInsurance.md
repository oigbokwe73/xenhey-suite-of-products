Your [Xenhey RentersInsurance page](https://www.xenhey.com/api/store/1AC101ABDC05446BB38E80DDCA5068C1) opens a **Customer Dashboard** with quote records and intake-edit controls. The strongest design direction is a simple journey from **rental details → belongings → coverage preferences → quote comparison → confirmed policy and proof of insurance**.

I reviewed its HTML and JavaScript. I did not submit quotes or test separately linked pages, carrier feeds or policy-binding integrations.

**Renters Insurance UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/m_3R3O19mUcWPGYzqk9QbILE5WMdtiBJ7hWO5tK64CpABweB0jqcVkrsnOcsemsgFuz_46AhypZK7kaoxBWvBSyG46-9-BCg6NeoHjVInI2BGpndMChO94FtOFfDhvM45oOvyzuiqKbIJNxpygis-1qnRAi8S2o8GghdMAcn-_F5w8JfTHuT79MPjWSTA9Ha?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/WPpiVhVltzcpxzfb6eNx9DBX_GyZ2rdPqWnjN3IsaTWKCbg2Yt-Z1Pa5O57lPbD7KA1St5n5Q4eY4_HctM_zmK4m4N-j5dl3OdwJPYXyDukZ6U5hb7xUYjx5EUaaXLkoL2WqD67PZMsYPGEEM7-87jLLn1Lu_qLNuxA6idKR6Eduoaajs0d-s-zbjii-R2ay?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/fUk15wzxGyV3RMs-SU0RWzMWB0LXLQ6_oMrm-sfTPW4_pmrueDifkIHz-ZnPyt38Jav4hzoQ0r7RxX4IgoRalo204tIAShtwJce0JgJGWknYcf4tyZKAhisJzgEQkIy08b7BnnWfaxOMef5XvQztmqMy2pxSc8xbjUi_1OH10Rx_KU-PugvvlZPfku80qlqX?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/_V87vuNq53FA5QGTLcaypFHn-34FRGIBB_O0k_WdGXZS0GQE4xX7mUVEA0sgt0kWInzOxpWQQcXrzjZd2tcaPMEjg-3jnPLUdFjotvUnmInq5JM6vtc88Jj1aZkTdgIG_CLSfDWkdp9kQFfiYK9Ft2VasvkgawVrf5wxPVJq3s118y10YMGS6IJlyK9D3lXJ?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/9nADBxQ3fRbOzg7jc1stMeycZ0IEOpOt6B0N2ZL98VRRHc6SzpN1BTDHJWc7xfwuzbAKC2E_ntEtmMMXXQKyQiPgQXqTftMxKeWYB5e5Ceo-2jJFtvVkvdEktLErG2B0fkBFhdPc2cVvCS2zAygcJYoLiOE9S8x8oQOxd_aVGFZ8YF36V0KmaGureYmlkG6B?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/Ts_nQcT6CiChXxcMckEeYWFqzdElDbxlVbkwYbgB2IAAIMa3Bo-QyzXN0XVPBgEjhJGx3FP9_ddPFlw5h7_sACJw84K1efoccvGKmzL07-UdHrjuTGf7L4OeliBIPfeQcvViDvqoFXSu-sykVlZgTXSd1rwaYvM9hhvHUCqi7Z32iiLcaRrfd55M2Atuuzc2?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/qYwFfW2OsIApYI36dFP9MpmlcJFlxbQ49G5RjmMCwNHvUHrVCRnknAKLTfOm01LiSB8_ZvDfn-72o4BkLbsyXP0QqBJSGWq6niHaj6pWcdxbZZR-UxRbpvrYlZqIJENPl9geTPJDSQxQ_mGKEmhzIqg5ytRDEy33llGVOPKOFPvU-KRJWqPJ0eprp_uBBfGo?purpose=fullsize)

| Screen               | What users should see                                                   | Main actions                     |
| -------------------- | ----------------------------------------------------------------------- | -------------------------------- |
| Customer dashboard   | Residence, quote progress, next action and policy status                | Continue quote, view policy      |
| Residence intake     | Rental type, location, move-in date and household details               | Edit, save draft                 |
| Belongings estimator | Furniture, electronics, clothing and valuables estimates                | Add category, review total       |
| Coverage selection   | Property limit, valuation method, liability, loss of use and deductible | Adjust preferences               |
| Quote comparison     | Carrier, coverage, term premium, billing and differences                | Compare, select                  |
| Proof of insurance   | Carrier-issued policy evidence and effective dates                      | Download, review sharing options |
| Policy management    | Documents, billing, renewal and change requests                         | View, request change             |
| Moving home          | New residence, move date and carrier review status                      | Request address change           |

**Evaluation of your current implementation**

Your seven-section intake covers applicant/location, residence/household, property inventory, coverage choices, risk/protections, endorsements and consent. All sections remain in one form, so values persist when users switch steps. The carrier comparison clearly labels its providers as synthetic. [Source: Xenhey Renters Insurance](https://www.xenhey.com/api/store/1AC101ABDC05446BB38E80DDCA5068C1).

| Finding                                                                                          | Recommended improvement                                                   |
| ------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| Dashboard counts are fixed: six quotes, one residence, two household members and one policy      | Calculate them for the selected customer                                  |
| Quote estimates display only as `/mo`                                                            | Add total term premium, payment schedule and applicable fees              |
| Save Draft requires all required fields                                                          | Allow incomplete drafts                                                   |
| Submit saves a separate browser-storage object                                                   | Update the shared intake collection and refresh the edited row            |
| Table uses `applicantName`, `city` and `state`; intake uses first/last name and residence fields | Map these fields explicitly                                               |
| Carrier Review links omit the chosen carrier                                                     | Carry `carrierId` and quote context into the next screen                  |
| Quote-status milestones are fixed                                                                | Use actual response and confirmation events                               |
| Source retains auto-insurance driver, vehicle and legacy-coverage schemas                        | Remove or isolate unrelated fields and review the discounts configuration |
| Move-in date and coverage date share one field                                                   | Separate them; they can differ                                            |
| Replacement-cost preference appears in two places                                                | Reconcile the selections to avoid contradictory answers                   |
| Checkbox hydration uses `Boolean(value)`                                                         | Parse values explicitly so `"false"` remains unchecked                    |

**1. A renter-focused dashboard**

Before purchase, prioritize:

* Selected residence
* Desired coverage start date
* Intake completion
* Outstanding questions
* Available carrier responses
* **Continue quote** and **Compare quotes**

After carrier confirmation, prioritize:

* Policy reference and carrier
* Effective and expiration dates
* Coverage summary
* Billing and renewal
* **Download proof of insurance**
* **Request a change**

Do not show an active policy merely because the customer selected a quote.

**2. Belongings estimator**

Your intake currently asks for a total value range. Add an optional category-based worksheet.

*Illustrative customer-entered estimates:*

| Category                    | Estimated value |
| --------------------------- | --------------: |
| Furniture                   |          $7,000 |
| Clothing and shoes          |          $5,000 |
| Electronics                 |          $4,000 |
| Kitchen and household items |          $3,000 |
| Sports and hobby equipment  |          $2,000 |
| **Total**                   |     **$21,000** |

Show this as an inventory estimate, not a recommended or guaranteed coverage amount. Let customers identify valuables for separate review, and keep receipts, photos and detailed inventories in secure storage.

**3. Coverage-comparison UI**

Make the components visible instead of relying on package names.

| Comparison field   | Display                                          |
| ------------------ | ------------------------------------------------ |
| Personal property  | Quoted limit                                     |
| Valuation          | Replacement cost or actual cash value, as quoted |
| Personal liability | Quoted limit                                     |
| Medical payments   | Quoted limit                                     |
| Loss of use        | Limit and relevant terms                         |
| Deductible         | Applicable amount and conditions                 |
| Optional coverage  | Included, excluded or pending review             |
| Premium            | Full term price and billing schedule             |
| Effective date     | Requested versus confirmed date                  |

Display carrier-confirmed details about household members and roommates; a household count alone should not imply everyone is insured.

**4. Lease requirements and proof of insurance**

Add a small **Rental requirements** section:

* Does the property manager request evidence of insurance?
* What requirements were supplied?
* Who should receive the evidence?
* What is the required date?
* Has the carrier reviewed the request?

Once available, display carrier-issued proof with its policy reference and effective dates. Sharing should require the customer to review the recipient and authorize delivery.

**5. Quote editing and refresh**

Complete the existing Edit workflow:

1. Load the selected intake with its stable ID.
2. Reset the form before loading another record to avoid leftover values.
3. Save all edited fields to the shared collection.
4. Update the applicant, residence and timestamp columns.
5. Mark older quotes as potentially outdated after material changes.
6. Request refreshed pricing through the configured integration.

Use separate labels for **Draft saved**, **Quote request submitted**, and **Carrier response received**.

**6. Moving and policy changes**

A useful renters-specific feature is a guided move request:

* New residence details
* Move date
* Requested coverage-change date
* Household or belongings changes
* Carrier review status
* Revised documents, when confirmed

Keep **change requested**, **under review**, and **effective** distinct. Saving a move request must not imply coverage has transferred.

For Xenhey, prioritize **renters-specific schema cleanup → complete draft saving → customer-specific records → clear coverage comparison → proof-of-insurance access → moving and policy-change workflows**.
