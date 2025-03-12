# Open Payment System

Healthcare services are typically billed at a very granular level. In order to simplify the the billing process,
we have created a set of Standard Service Packages (SSPs) that consolidate all medical services, materials, and 
fees associated with a healthcare procedure into a single bundled code.

[Standard Service Packages (SSPs)](https://servicepackages.health/) consolidate all medical services, materials, 
and fees associated with a healthcare procedure into a single bundled code. They are open-source, 
patient-first, compatible with existing transaction standards and clearly distinguish between services, encounters, 
and episodes. 

Each SSP captures the average cost of a service across many historical patients. Billing by service bundle instead of
by discrete service allows for faster, simpler, and more transparent billing and payment while still capturing 
care costs and revenue accurately.

## What makes up a Standard Service Package?

Standard Service Packages (SSPs) are a bundle of codes that represent what actually gets billed alongside a primary CPT code. These include revenue codes, professional fees, labs, drugs, etc. 
SSPs adhere to the following heuristic:
- Clinical Similarity & Relevance
- Cost Similarity
- Consumer Comprehension & Relevance

## What is included in each SSP?
- SSP ID - A unique, five digit alphanumeric code representing an entire bundled service that can be billed in place of a CPT code.
- Descriptions, both clinical and patient-facing, of the service package. 
- Categorization and tagging related to the status, cost, frequency and service type of that service package.
- List of bundled services, codes & fees that are billed in association with the primary service.

In short, patients are billed for a single service bundle instead of a long list of individual services, materials, and fees.
But the bundles are designed to accurately capture the true cost of the service as delivered to many historical patients.

In the future, we will also be releasing code that lets a provider recalculate the cost of each service bundle based on their
own historical data.

## SSP Machine Readable Data

- CSV: [List of SSPs, including descriptions, categories, and average payment amounts](./ssps/ssp_list.csv)
- CSV: [List of discrete healthcare services and fees associated with each SSP bundle](./ssps/ssp_contents.csv)

## Quick Reference List of SSPs

Each of these packages represents a single service bundle that can be billed in place of a CPT code. Each package is made up of a primary service code and a set of associated services, materials, and fees.

SSPs are designed to capture the average cost of a service, including all associated services, materials, and fees.
Since the cost of a service can vary based on the patient's condition, these packages are build on historical patient
averages. Each code and fee associated with SSP package contains a correlation of how often that service is used in 
conjunction with the primary service.

| SSP   | Category                           | Name                                                         | Average Payment | Average Charges | Average Optional Charges | [APC Crosswalk](https://www.cms.gov/cms-guide-medical-technology-companies-and-other-interested-parties/payment/opps) |
|-------|------------------------------------|--------------------------------------------------------------|-----------------|-----------------|--------------------------|-----------------------------------------------------------------------------------------------------------------------|
| DE000 | Dermatology                        | Percutaneous Breast Biopsy                                   | 1544.75         | 9229.27         | 873.33                   | [5072](https://www.aapc.com/codes/apc-codes/5072)                                                                                                                  |
| EN000 | ENT                                | Tonsil and Adenoid Removal (Child Under 12)                  | 5579.71         | 19998.14        | 117.80                   | [5165](https://www.aapc.com/codes/apc-codes/5165)                                                                                                                  |
| GA000 | Gastrointestinal                   | Colonoscopy via Stoma                                        | 983.59          | 9550.36         | 176.21                   | [5311](https://www.aapc.com/codes/apc-codes/5311)                                                                                                                  |
| GA002 | Gastrointestinal                   | Colonoscopy                                                  | 1058.09         | 9283.91         | 525.54                   | [5312](https://www.aapc.com/codes/apc-codes/5312)                                                                                                                  |
| GA007 | Gastrointestinal                   | Esophagogastroduodenoscopy, Simple                           | 863.69          | 8662.33         | 743.25                   | [5301](https://www.aapc.com/codes/apc-codes/5301)                                                                                                                  |
| GA010 | Gastrointestinal                   | Hernia Repair - Laparoscopic                                 | 5497.59         | 49255.46        | 784.92                   | [5361](https://www.aapc.com/codes/apc-codes/5361)                                                                                                                  |
| GA011 | Gastrointestinal                   | Hernia Repair - Non-Laparoscopic                             | 3296.34         | 32460.58        | 262.90                   | [5341](https://www.aapc.com/codes/apc-codes/5341)                                                                                                                  |
| MS000 | MSK                                | Knee Arthroplasty 1                                          | 12539.82        | 81365.01        | 370.58                   | [5115](https://www.aapc.com/codes/apc-codes/5115)                                                                                                                  |
| MS002 | MSK                                | Hip Arthroplasty                                             | 12539.82        | 81911.84        | 421.11                   | [5115](https://www.aapc.com/codes/apc-codes/5115)                                                                                                                  |
| OP000 | Ophthalmology                      | Cataract Removal with Intraocular Lens Insertion             | 2220.35         | 14340.20        | 323.63                   | [5491](https://www.aapc.com/codes/apc-codes/5491)                                                                                                                  |
| PU000 | Pulmonology                        | Bronchoscopy                                                 | 1617.14         | 10868.53        | 3456.17                  | [5153](https://www.aapc.com/codes/apc-codes/5153)                                                                                                                  |
| RA000 | Radiology                          | X-Ray                                                        | 89.67           | 1736.39         | 79.99                    | [5521](https://www.aapc.com/codes/apc-codes/5521)                                                                                                                  |
| RA003 | Radiology                          | Advanced CT Imaging 3                                        | 87.98           | 1400.04         |                          | [5521](https://www.aapc.com/codes/apc-codes/5521)                                                                                                                  |
| RA004 | Radiology                          | CT of Abdomen and Pelvis                                     | 328.32          | 7806.90         | 1140.56                  | [5572](https://www.aapc.com/codes/apc-codes/5572)                                                                                                                  |
