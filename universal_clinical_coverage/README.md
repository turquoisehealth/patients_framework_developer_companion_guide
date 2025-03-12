# Universal Clinical Coverage

Universal Clinical Coverage (UCC) replaces prior authorizations with open-source, rules-based, real-time coverage determinations for Standard Service Package (SSP). It is a provider- and patient-friendly reference library and rule set, aggregating and simplifying widely accepted clinical coverage criteria specific to each 
Standard Service Package.

## The Coverage Determination Library
For each Standard Service Package (SSP), there is a corresponding set of Universal Clinical Coverage (UCC) rule set. Each rule set includes one or more coverage scenarios that reflect the most common coverage criteria for that service.

For example, a patient may require a laparoscopic hernia repair:
- All the discrete services required to perform the procedure are bundled into a Standard Service Package (SSP) with id GA010.
- The patient can qualify for this procedure based on the Universal Clinical Coverage (UCC) rule set, but there are multiple scenarios that can qualify a patient for this procedure based on their diagnosis and required treatment:
  - GA010.1 Inguinal, Femoral, Ventral
  - GA010.2 Hiatal
  - GA010.3 Umbilical
- Each scenario has a different set of qualifying diagnosis and procedure codes that determine if the patient is eligible for the procedure.

## UCC Machine Readable Data

- JSON: [Structured data listing each SSP and the related Universal Clinical Coverage rules associated with it](./ucc/ssp_ucc.json)
- CSV: [List of SSPs, including descriptions, categories, and average payment amounts](../open_payment_system/ssps/ssp_list.csv)
- CSV: [List of discrete healthcare services and fees associated with each SSP bundle](../open_payment_system/ssps/ssp_contents.csv)

## Quick Reference List of Universal Clinical Coverage Rule Sets

|SSP ID|SSP Name                                        |Coverage Scenario Code|Coverage Scenario Title                        |Qualifying Diagnosis Count|Qualifying Procedure Count|
|------|------------------------------------------------|----------------------|-----------------------------------------------|--------------------------|--------------------------|
|RA000 |X-Ray                                           |RA000.1               |Comprehensive Skeletal Radiography             |507                       |20                        |
|GA000 |Colonoscopy via Stoma                           |GA000.1               |Colonoscopy Via Stoma                          |575                       |19                        |
|EN000 |Tonsil and Adenoid Removal (Child Under 12)     |EN000.1               |Tonsilloadenoidectomy                          |23                        |12                        |
|MS000 |Knee Arthroplasty 1                             |MS000.1               |Knee Arthroplasty                              |545                       |17                        |
|GA007 |Esophagogastroduodenoscopy, Simple              |GA007.1               |Esophagogastroduodenoscopy                     |782                       |40                        |
|OP000 |Cataract Removal with Intraocular Lens Insertion|OP000.1               |Cataract Extraction with Intraocular Lens (iol)|245                       |34                        |
|GA010 |Hernia Repair - Laparoscopic                    |GA010.1               |Inguinal, Femoral, Ventral                     |4                         |33                        |
|GA010 |Hernia Repair - Laparoscopic                    |GA010.2               |Hiatal                                         |7                         |21                        |
|GA010 |Hernia Repair - Laparoscopic                    |GA010.3               |Umbilical                                      |3                         |12                        |
|PU000 |Bronchoscopy                                    |PU000.1               |Bronchoscopy with Specific Intervention        |69                        |19                        |
|GA011 |Hernia Repair - Non-Laparoscopic                |GA011.1               |Inguinal, Femoral, or Ventral                  |4                         |30                        |
|GA011 |Hernia Repair - Non-Laparoscopic                |GA011.2               |Hiatal                                         |7                         |18                        |
|GA011 |Hernia Repair - Non-Laparoscopic                |GA011.3               |Umbilical                                      |3                         |12                        |
|DE000 |Percutaneous Breast Biopsy                      |DE000.1               |Percutaneous Breast Biopsy                     |10                        |13                        |
|MS002 |Hip Arthroplasty                                |MS002.1               |Hip Arthroplasty                               |146                       |11                        |
|GA002 |Colonoscopy                                     |GA002.1               |Colonoscopy                                    |575                       |20                        |
