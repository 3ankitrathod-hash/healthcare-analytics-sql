# Healthcare Analytics SQL Project

A reproducible MySQL 8 portfolio project modeling a small fictional healthcare organization and answering reporting questions about patient geography, provider experience, billing, and department revenue.

> **Privacy:** All committed seed records are fictional. Never commit real patient, provider, or personal health information.

## Project files
- `healthcare_schema.sql` — creates the practice database and relational tables.
- `healthcare_sample_data.sql` — inserts fictional rows for local testing.
- `healthcare_queries.sql` — reporting examples using filtering, joins, aggregation, conditional aggregation, and a reusable view.
- `.github/workflows/mysql-validation.yml` — runs the schema, seed data, and queries against MySQL 8 on pushes and pull requests.

## Run locally
Use a disposable MySQL 8 environment. From this directory, run:

```bash
mysql -u root -p < healthcare_schema.sql
mysql -u root -p < healthcare_sample_data.sql
mysql -u root -p < healthcare_queries.sql
```

The scripts use the `healthcare_analytics_practice` database. The schema does not drop an existing database. The sample records are fictional and for practice only.

## Questions answered
1. Which patients are listed in Bengaluru/Bangalore?
2. Which active doctors have more than ten years of experience?
3. How many patients are assigned to each doctor, including doctors with no patients?
4. What paid amount is recorded by payment mode?
5. Which departments have the highest paid revenue?
6. What does the `vw_doctor_revenue` view report for each doctor?

## Data model
Departments, doctors, patients, appointments, bills, and medications are connected with primary and foreign keys. The sample is deliberately small and demonstrates SQL techniques; it is not representative of a real healthcare provider.

## Validation
GitHub Actions attempts to create the schema, load the fictional seed records, execute the reporting queries, and assert selected totals. Check the Actions tab for the actual result. Passing automated SQL checks verifies reproducibility only, not clinical or operational validity.
