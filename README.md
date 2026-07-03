# Provider Directory Accuracy Audit

An Excel and Power BI project that reconciles provider source data against a simulated directory output to identify and quantify data quality discrepancies.

## Why This Matters

Health plans are required to keep provider directories accurate. CMS national reviews have found that roughly half of provider directory locations contain at least one inaccuracy, most commonly wrong phone numbers, incorrect addresses, or outdated patient acceptance status. Under the No Surprises Act, plans must verify every provider record at least once every 90 days and process updates within two business days. This project simulates that reconciliation process, comparing a provider source dataset against a directory output to identify discrepancies and measure accuracy against industry compliance benchmarks.

## Data Sources

**Provider Source Data:** Pulled from the NPPES (National Plan and Provider Enumeration System) API, the official public registry maintained by CMS for every healthcare provider in the United States. This served as the source of truth for provider name, specialty, and practice address.

**Directory Output Data:** Simulated for this project. Real member facing directories are not publicly available in a comparable format, so a copy of the source data was modified to introduce realistic errors, matching the error types identified in CMS's own provider directory audits (wrong phone numbers, incorrect addresses, incorrect specialty listings, and inaccurate network or patient acceptance status).

## Methodology

1. Pulled 200 provider records from the NPPES API for a single metro area using Power Query in Excel.
2. Created a duplicate dataset to represent the directory output, and introduced errors into approximately 15-20% of records across five fields: phone number, address, specialty, network status, and patient acceptance status.
3. Used XLOOKUP to match records between the two tables on NPI (National Provider Identifier), the unique ID assigned to every provider, and built comparison columns to flag mismatches field by field.
4. Applied conditional formatting to visually flag every discrepancy, and summarized results using a pivot table.
5. Brought the cleaned data into Power BI to build a two page report: an executive summary view and an operational work queue view.

## Key Findings

[To be filled in once analysis is complete]

## Tools Used

Excel (Power Query, XLOOKUP, pivot tables, conditional formatting), Power BI (Power Query, star schema modeling, DAX)

## Files

- Provider_Directory_Audit.xlsx
- Provider_Directory_Audit.pbix
