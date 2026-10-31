# Healthcare Data Governance and Cleaning

## What I did
- Loaded the synthetic patient sample (10 records, 10 fields).
- Built a data dictionary classifying each field (identifier, demographic, clinical).
- Validated types, ranges, missing values, and duplicate PatientIDs.
- Applied cleaning rules without inventing clinical values.

## Why the data is de-identified
No names, phone numbers, addresses, emails, or exact dates of birth. PatientID is a pseudonymous code (PAT-xxx) with no link to a real person. The dataset is labelled synthetic training data. Age and gender are the only quasi-identifiers, and with 10 records and no location data, re-identification risk is low.

## Findings
- Missing values: 0
- Duplicate PatientIDs: 0
- Out-of-range or invalid values: 0
- Exception log is empty because all checks passed.

## Cleaning rules applied
1. Trimmed extra spaces in text fields.
2. Split BloodPressure into Systolic and Diastolic.
3. Checked systolic > diastolic (0 failures).
4. Added Readmitted_Flag (Yes=1, No=0); original column kept.
5. No values were imputed or changed.

## Files
- cleaning_notebook.ipynb
- clean_patient_records.csv
- data_dictionary.csv
- exception_log.csv