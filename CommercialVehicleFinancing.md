Your [Xenhey Commercial Vehicle Financing page](https://www.xenhey.com/api/store/3C5CE7C211454CA2AFD0C5AF620844BA) opens a **Customer Dashboard** with an application table and financing progress tracker. The strongest improvement is to make the **selected vehicle, financing terms, closing requirements and delivery status** the center of the experience.

I reviewed its HTML and JavaScript. I did not submit applications or test separately linked pages, record feeds or lender integrations.

**Commercial Vehicle Financing UI examples**

These images are design inspiration, not screenshots of your Xenhey implementation.

![Image](https://images.openai.com/static-rsc-4/yD9Gwcrq--i9S34HyckfvCUYne-LGxP_qQlta7plAARnp1DxjPFcT8nxraTdbrqN7nGsiR977-TRFF6O0mEBnKNctn1M_ivR8KUJW_xA5ALmYVU2ToVxyEDVleSm_ZWda7aA-quBzjowzqceYYEVpuyq9z9RPnRZCippv8b9ftjmbDTbksYbC78Xl6U8RmXw?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/df2bZe2sKbLGwDDZ7jrf5TNV3_XyiEpVxU-bpFdcneLYz0ve1K7YjckW87GhtPXQ7CaRc8ejTiJXMQTNo9CC6kTvkf4HBJj9KY5RhymsAlcURTE5OfhO1UAIRkcn0S-5T0XhWw0YBtRdlpmThHeGMrhboIt3cOpA9pkMnwVKyhhtHMxeOl0hERIx_7ha0UeA?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/MlqpHGoTlxXwWaRdW46Rv3XDGxhNPZ3xAGPOk4KlKJ8lDNRXr862MGZ2Mb_kg5PsnOK6qSvEWb35jcvHS67G4ax-4hRMyh4lmeWmDV9mdPSfYMUoO-spVFR1mWnyt6fYV03afwUZdyrCsRSKtq5DP-tFVpXYzU9CyNShoIeQWO8AdPJs2IysHXVrIxoA-bkf?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/SMa7SPvjZl0m0x792wXxhR8Xl8OaosbHWOmMyV93d5lhpd7CsLgB0uIHc0vGE19p9-hmzWHPhRZiyzctBVbhzapQseoQNusOfCjEtLtpyY9fAW_QzD3g4gdrlHRADUy8QAbO5FgVyVTph3G6oobTcv_tCdoHprlhzg0spreCMby2DdgUrmvKKRIGDGfza4se?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/-Uwv43r_JGWeJe6ZjyymPnO8FuQEUn5YilnoKekyBOgF1RDrMzstIZLRehkoBSVnSRLhBYCA0cITxynhBofiEU2ayZW9PRqcwxr2Tq1D1ZNKXzZoD2sxUV3tSeOvM0K9WHaEcl7rN3WMlHzU-QPJomSPzzcKx5ug5Y23UZKnNKNnLUM7RMooAEg_72kkJnb3?purpose=fullsize)

![Image](https://images.openai.com/static-rsc-4/tf8rRWdDvNpUJf5vYVg9mONSSff_uCsh7_ez_G4V1nxBsK_B6Ud4veaxF8HpvAMh9Srn2JVUjCDf1w83AtZAAHtgP3KBIL8LGyBk8aNKjmLfulkMG0TTNWxYgTlpgod28TwznLmD6hKoK1Kt6tcUKUCb7FOShWyRkBj2zsramAGgqHQZNyLbrEpK9Ka7T86w?purpose=fullsize)

| Screen               | What users should see                                                     | Main actions                           |
| -------------------- | ------------------------------------------------------------------------- | -------------------------------------- |
| Customer dashboard   | Selected vehicle, requested financing, stage and outstanding requirements | Continue application, resolve requests |
| Vehicle details      | Photo, year, make, model, mileage, condition and business use             | Edit vehicle, attach quote             |
| Dealer and quote     | Dealer contact, purchase price, expiration and supporting documents       | Review, replace quote                  |
| Financing request    | Purchase-cost breakdown, down payment, trade-in and requested amount      | Adjust request, review                 |
| Offer comparison     | Approved amount, term, payment, rate, fees and conditions                 | Compare, select offer                  |
| Closing checklist    | Signatures, insurance, title and payment requirements                     | Provide evidence, sign                 |
| Funding and delivery | Dealer payment, delivery appointment, inspection and acceptance           | Track, confirm, report issue           |
| Loan servicing       | Balance, next payment, statements and vehicle-linked requests             | Make payment, view statement           |

**Evaluation of your current page**

The implementation includes an eight-step vehicle-specific intake, explicit field types, searchable tables, CSV export and controls that load a selected sample application into the form. It also covers vehicle condition, mileage, dealer details, business use, insurance and operating-authority review. [Source: Xenhey Commercial Vehicle Financing](https://www.xenhey.com/api/store/3C5CE7C211454CA2AFD0C5AF620844BA).

| Finding                                                                             | Recommended improvement                                        |
| ----------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| Dashboard vehicle and requested amount come from the first record                   | Bind the dashboard to the selected customer and application    |
| Stage and next-review date are hard-coded                                           | Calculate them from actual workflow status                     |
| Customer table includes internal risk tiers                                         | Keep internal risk assessments in the operations workspace     |
| Dashboard table lacks View/Edit actions                                             | Add record-specific links to the application                   |
| Table displays `year` and `make`, while intake uses `vehicleYear` and `vehicleMake` | Define consistent mappings so edits appear correctly           |
| Intake supports one vehicle                                                         | Add repeatable vehicle entries if fleet purchases are in scope |
| Wizard navigation redraws fields without saving current input                       | Preserve all sections in a working draft                       |
| Revisiting a step reloads the original selected record                              | Restore the latest edited values                               |
| Save Draft stores only the active section                                           | Save the entire application under its stable ID                |
| Final submission uses the generic form-save handler                                 | Validate every section and confirm backend submission          |
| Offers, payments and delivery screens reuse the application table                   | Build dedicated views and datasets for each workflow           |

**1. Vehicle-centered dashboard**

Use a vehicle summary card beside the application status.

The card should include:

* Vehicle photograph or placeholder
* Year, make, model and body type
* New/used condition and mileage
* Dealer
* Purchase price
* Requested financing
* Desired delivery date

Below it, show the next required action, such as **“Provide updated insurance evidence”**, with a direct link to that request.

For customers financing multiple vehicles, add a vehicle selector and show status per vehicle.

**2. Vehicle and dealer workspace**

Use tabs for **Vehicle**, **Quote**, **Inspection**, **Insurance**, and **Documents**.

| Vehicle information            | Quote information              |
| ------------------------------ | ------------------------------ |
| Year, make and model           | Dealer and contact             |
| Vehicle type and configuration | Quote reference and expiration |
| Mileage and condition          | Vehicle price                  |
| VIN/reference                  | Upfit or accessory costs       |
| Intended business use          | Taxes and fees                 |
| Operating location             | Trade-in and delivery details  |

Store photographs and document contents through secure file handling; keep references in the application record.

**3. Financing-request breakdown**

Make the requested amount understandable rather than asking users to enter unrelated totals.

*Illustrative transaction:*

| Component                  |       Amount |
| -------------------------- | -----------: |
| Vehicle purchase price     |      $90,000 |
| Upfit and accessories      |       $8,000 |
| Taxes and fees             |       $6,000 |
| **Total transaction cost** | **$104,000** |
| Cash down payment          |     −$15,000 |
| Net trade-in equity        |      −$9,000 |
| **Requested financing**    |  **$80,000** |

Separate trade-in value from any existing payoff. Show which costs the provider permits financing, and flag differences between the calculated request and the entered amount.

**4. Application and offer review**

Retain your eight sections:

1. Business profile
2. Vehicle and dealer
3. Financing request
4. Operations and compliance
5. Financial profile
6. Ownership and control
7. Documents and review
8. Consent and submission

Add a final summary displaying the actual entered values with **Edit section** links.

The offer screen should present lender-issued terms as read-only information:

* Approved amount and required down payment
* Term and payment frequency
* Scheduled payment
* Applicable rate and fees
* Balloon or residual obligation, if applicable
* Collateral and guarantee requirements
* Outstanding conditions and expiration

Label payment estimates clearly and keep them separate from confirmed offers.

**5. Closing, funding and delivery**

Use distinct statuses so one completed activity does not imply that everything is complete.

| Area       | Example statuses                              |
| ---------- | --------------------------------------------- |
| Agreement  | Preparing, awaiting signature, completed      |
| Insurance  | Requested, submitted, verified                |
| Title/lien | Review pending, exception, confirmed          |
| Funding    | Awaiting authorization, processing, confirmed |
| Delivery   | Scheduled, delivered, issue reported          |
| Acceptance | Inspection pending, accepted, exception       |

The sequence should follow the lender’s requirements. Delivery, acceptance and funding may depend on each other differently across transactions.

Provide a delivery checklist for vehicle identity, odometer reading, condition, accessories and acceptance evidence.

**6. Active-loan dashboard**

After funding, replace the application tracker with:

* Outstanding principal
* Next payment amount and due date
* Payment history
* Statements and agreement documents
* Vehicle details
* Insurance-renewal requests
* Title-related service requests
* Provider-supported payoff inquiries

Keep scheduled, processing and posted payments distinct. Any payoff amount should come from a dated provider quote.

For Xenhey, prioritize **complete draft saving → consistent vehicle-field mappings → vehicle-specific dashboard → financing-cost breakdown → offer comparison → confirmed closing and delivery states**.
