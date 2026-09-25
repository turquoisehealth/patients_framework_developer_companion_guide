# Open Payment System

Healthcare services are typically billed at a very granular level. In order to simplify the billing process,
we have created a set of Standard Service Packages (SSPs) that consolidate all medical services, materials, and
fees associated with a healthcare procedure into a single bundled code.

[Standard Service Packages (SSPs)](https://servicepackages.health/) are open-license, patient-first, and compatible with current transaction standards including the various UB-04 bill types and CMS-1500. They can be structured at three levels of care: individual procedures or discrete clinical services (items & services), single visit procedures (encounters), or multi-visit care journeys for a specific condition (episodes).

Each SSP captures the average cost of a service across many historical patients. Billing by service bundle instead of by discrete service allows for faster, simpler, and more transparent billing and payment while still capturing care costs and revenue accurately.

## What makes up a Standard Service Package?

Standard Service Packages (SSPs) are a bundle of codes that represent what actually gets billed alongside a primary CPT code, known as the 'anchor' code. These include revenue codes, professional fees, labs, drugs, etc.
SSPs adhere to the following heuristic:
- Clinical similarity & relevance
- Cost comparability
- Consumer comprehension & relevance

## What are clinical sub-variants?

Clinical sub-variants are complexity tiers that sit inside a single SSP, defined by clinical similarity and validated by cost. They capture clinical complexity without splitting an SSP into multiple patient-facing packages, keeping the catalog easy for consumers to navigate. Not every SSP has sub-variants; they are defined only where a meaningful complexity split exists. Where they do exist, each sub-variant maps to its own anchor code(s), and the aggregate SSP price is calculated using a national average case-mix adjustment across sub-variants, weighted by the relative reimbursement of each anchor code.

## What is included in each SSP?
- SSP ID - a unique, five digit alphanumeric code representing an entire bundled service that can be billed in place of a CPT code.
- Descriptions - a consumer-facing title and description, at both the grouper and clinical sub-variant level.
- Shoppability score - the degree to which a patient can shop for the service.
- SSP type - the level of care the package is structured at: item & service, encounter, or episode.
- APC / DRG - the CMS reference classification the package crosswalks to, outpatient or inpatient.
- Bundled contents - the services, codes & fees that are billed in association with the anchor code.

What the bundle contains depends on the SSP type. An item & service contains the anchor code only, captured across
both the professional and facility claim. An encounter contains the anchor code plus its ancillary line items, and
those line items can themselves be items & services. An episode is a multi-visit patient journey and can contain both
encounters and items & services.

In short, patients are billed for a single service bundle instead of a long list of individual services, materials, and fees. But the bundles are designed to accurately capture the true cost of the service as delivered to many historical patients.

In the future, we will also be releasing code that lets a provider recalculate the cost of each service bundle based on their own historical data.

## How do we define 'shoppability'?

Turquoise's Shoppability score is a single, service-level score that quantifies the degree to which a patient can proactively plan or shop for a service in a market with sufficient access, and the degree to which price is a key lever in their decision against other factors. The relative shoppability of a service is determined by various inputs such as the availability and substitutability of cost-effective alternatives and the emergent nature of the service.

## SSP Machine Readable Data

- CSV: [List of SSPs, including descriptions, categories, and average payment amounts](./ssps/ssp_list.csv)
- CSV: [List of discrete healthcare services and fees associated with each SSP bundle](./ssps/ssp_contents.csv)
- CSV: [List of clinical sub-variants defined and their associated anchor codes](./ssps/ssp_clinical_sub_variants.csv)

## SSP Library Coverage

We have released a subset of our SSP library, with more being published on a rolling basis. The following table
reflects the data in the CSVs linked above, by disease area and SSP type.

Each code and fee associated with an SSP package carries a correlation of how often that service is used in
conjunction with the anchor code, known as the association rate.

| Disease Area                 |     TOTAL |       I&S | Encounter |
|------------------------------|-----------|-----------|-----------|
| Behavioral Health            |         3 |         2 |         1 |
| Cardiac & Vascular           |        12 |         1 |        11 |
| Dermatology                  |         8 |         0 |         8 |
| Ear, Nose & Throat           |         3 |         1 |         2 |
| Emergency / Trauma           |         3 |         3 |         0 |
| Gastroenterology             |         7 |         0 |         7 |
| General Medicine             |         1 |         1 |         0 |
| Gynecology                   |         4 |         0 |         4 |
| Hematology                   |         1 |         0 |         1 |
| Lab / Pathology              |         1 |         1 |         0 |
| Musculoskeletal              |        33 |         1 |        32 |
| Neurology                    |         7 |         3 |         4 |
| Obstetrics                   |         1 |         0 |         1 |
| Oncology / Radiation Therapy |         1 |         0 |         1 |
| Ophthalmology                |         5 |         1 |         4 |
| Pulmonology                  |         3 |         1 |         2 |
| Radiology                    |        18 |        17 |         1 |
| Urology / Nephrology         |        11 |         0 |        11 |
| **Total**                    |   **122** |    **32** |    **90** |
