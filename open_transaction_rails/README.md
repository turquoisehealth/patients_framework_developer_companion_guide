# Open Transaction Rails for Healthcare Payments

The Health Insurance Portability and Accountability Act of 1996 codified the ASC X12 EDI standards as a required digital format for communicating healthcare financial information.
We’ve long outgrown this decades-old, proprietary set of standards. The elimination of administrative burden in the United States requires a path towards a new, open transaction standard that is cross-compatible and backwards compatible with the EDI-backed system we use today.

We propose replacing legacy ASC X12 transaction communications with the modern, open replacements proposed 
by the [FHIR project’s Financial Module](https://build.fhir.org/financial-module.html). Each legacy X12 transaction (checking patient eligibility, submitting a claim, receiving a payment, etc) has a direct FHIR replacement.

## API Specifications

These are the mappings between each legacy X12 transaction type and the modern replacement's FHIR API specification:

| Legacy X12 Transaction Set | Name                                        | FHIR Financial Module API Resource                                                   |
| -------------------------- | ------------------------------------------- |--------------------------------------------------------------------------------------|
| [270](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)                        | Eligibility Inquiry                         | [CoverageEligibilityRequest](https://hl7.org/fhir/coverageeligibilityrequest.html)   |
| [271](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)                        | Eligibility Response                        | [CoverageEligibilityResponse](https://hl7.org/fhir/coverageeligibilityresponse.html) |
| [276](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)                        | Claim Status Inquiry                        | [Task (code=status)](https://hl7.org/fhir/task.html)                                 |
| [277](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)                        | Claim Status Response                       | [Task (output=status code)](https://hl7.org/fhir/task.html)                          |
| [278](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)                        | Prior Authorization Request                 | [Claim (use=preauthorization)](https://hl7.org/fhir/claim.html)                      |
| [278 Response](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)               | Prior Authorization Response                | [ClaimResponse](https://hl7.org/fhir/claimresponse.html)                             |
| [820](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)                        | Payment/Remittance Advice                   | [PaymentReconciliation](https://hl7.org/fhir/paymentreconciliation.html)             |
| [834](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)                        | Benefit Enrollment and Maintenance          | [EnrollmentRequest](https://hl7.org/fhir/enrollmentrequest.html)                     |
| [835](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)                        | Health Care Claim Payment/Remittance Advice | [PaymentNotice](https://hl7.org/fhir/paymentnotice.html)                             |
| [837P, 837I, 837D](https://en.wikipedia.org/wiki/X12_Document_List#X12N:_Insurance)           | Health Care Claim (Professional)            | [Claim](https://hl7.org/fhir/claim.html)                                             |
| Novel                      | Good Faith Estimate Provider Collaboration  | FHIR-Based, Releasing Q2 2025                                                        |
| Novel                      | Advanced EOB Bundling and Processing        | FHIR-Based, Releasing Q2 2025                                                        |
| Novel                      | Direct to Patient GFE & AEOB Module         | FHIR-Based, Releasing Q2 2025                                                        |
| Novel                      | Direct to Patient Balance Module            | FHIR-Based, Releasing Q2 2025                                                        |

## Implementation Examples - Coming Soon

 We will update this page to provide an open source examples of each transaction type in
 Q2 2025. This will make it easy for any software developer to start from a common sense recipe of 
 how to implement basic transactions, like checking a patient’s insurance coverage, filing a claim, 
 or making a payment.