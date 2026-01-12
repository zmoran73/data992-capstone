# Data Dictionary (Template)

Instructions
- For each dataset used in the project list fields below. Keep this file as the canonical definition for all downstream users.

Dataset: [dataset_name.csv or dataset_name.table]
Source: [URL or data provider]
License: [license or terms of use]
Description: [short description of dataset purpose & coverage]

Field definitions (table)

| field_name     | description                                 | type     | allowed_values / example | source / derivation           | missing_value_code | notes |
| -------------- | ------------------------------------------- | -------- | ------------------------ | ----------------------------- | ------------------ | ----- |
| id             | Unique identifier for record                | integer  | 1001                    | provider id field             | NA                 | primary key |
| timestamp      | Event timestamp (UTC)                       | datetime | 2024-09-01T12:34:56Z    | provider system               | NULL               | ISO 8601 format |
| user_age       | Age of the user in years                     | integer  | 34                      | survey / user profile         | -1                 | validate range 0–120 |
| country_code   | ISO 3166-1 alpha-2 country code             | string   | "US", "CA"              | provider or geolocation lookup| ""                 | uppercase |
| measurement_x  | Measurement X (description + units)         | float    | 12.34                   | sensor reading                | NaN                | units: meters |
| category_label  | Categorical label used for grouping         | string   | "A", "B", "C"           | derived                      | "unknown"          | mapping documented below |

Derived fields (if any)
- derived_score: numeric — formula: normalized sum of metrics A and B; range 0–1.

Validation rules and notes
- Primary key uniqueness: id must be unique per dataset.
- Timestamp completeness: all records must contain a valid ISO 8601 timestamp.
- Range checks: user_age should be between 0 and 120; flag records outside range for review.

Example CSV header
field_name,description,type,allowed_values/example,source/derivation,missing_value_code,notes

Change log
- 2026-01-12 — Initial template created by zmoran73

---
