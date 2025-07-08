# mapdata_finalization_notebooks

## Repository Summary: mapdata_finalization_notebooks

A comprehensive data processing pipeline for finalizing PPP (Paycheck Protection Program) loan data with geographic mapping and categorical encoding. The repository contains Jupyter notebooks that process raw PPP data through multiple stages:

**Data Pipeline Flow:**

1. **Data Cleaning & Labeling** (`main_label_pipe23.ipynb`) 
   - Takes raw PPP loan data as input
   - Cleans and standardizes the dataset
   - Handles missing values and data quality issues

2. **Hash Encoding** (`main_hashing23.ipynb`) 
   - Further processes cleaned loan data
   - Creates unique hash values for each loan entry
   - Generates composite key codes combining:
     - Industry classification
     - Industry subsector
     - Loan amount ranges
     - Job count ranges
     - Business type
     - Business age categories
     - Loan type (PPP/PPS)

3. **Geographic Integration & Database Assembly** (`main_concat23.ipynb`)
   - Merges selected columns from label pipe and hash pipe outputs
   - Integrates geographic data (coordinates, full addresses, FIPS codes) from external repository
   - Creates consolidated main database
   - Splits final dataset into individual state-level database files

**Output:** State-specific databases ready for geographic analysis and mapping visualization, with efficient categorical encoding for analytical queries.

---
**Note:** The repository also contains older versions of the pipeline (`main_label_pipe.ipynb`, `main_hashing.ipynb`, `main_concat.ipynb`) that process 2021 loan data, while the updated files with "23" suffix process 2023 loan data.