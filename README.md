# mapdata_finalization_notebooks

**Processes Raw Data obtained from SBA Public Data Directory for the
release of PPP Loan Data in 2021 and 2023.**

**Scripts:**

> **<u>main_label_pipe.ipynb</u> -** processes raw data through pipeline
> of cleaning, formatting, and integrating associated data sources to
> expand on given database.
>
> **<u>main_HASHING.ipynb</u> -** creates HASHcode column for dataframe
> with variables for Industry, Industry Subsector, Loan Range, Job
> Range, Business Type, Business Age, and PPP/PPS program.
>
> **<u>main_concat.ipynb</u> –** combines final outputs of
> main_label_pipe, main_hashing, and Geo processed FIPS files for
> finalized output to be used in state aggregation.

**Updates/comparisons**

> **<u>column_value_checks.ipynb</u> –** Exploratory Data Post Pipe
> process:
>
> DataFrame: (Grouped) SBA Office Label, Code, (Aggregated) Loan
> Number(count).
>
> Plot: Box, SBA Office Label vs Current Approval Amount(sum)
>
> DataFrame: Grouped (Borrower State), (Aggregated) Loan Count, Current
> Approval Amount, Average Loan Amount
>
> Plot: Box, Borrower State vs Current Approval Amount (values)
>
> Plot: Bar, Borrower State vs Current Approval Amount (sum)
>
> DataFrame: (Grouped) Servicing Lender, Location ID, (Aggregated) Loan
> Number(count), Current Approval Amount(sum), Average Loan Amount
>
> DataFrame: (Grouped) Originating Lender, Location ID, (Aggregated)
> Loan Number(count), Current Approval Amount(sum), Average Loan Amount
>
> DataFrame: Lender Match, filtered where Servicing Lender !=
> Originating Lender
>
> DataFrame: From filtered Lender Match DataFrame (Grouped) Servicing
> Lender, Location ID, Originating Lender, (Aggregated) Loan
> Number(count), Current Approval Amount(sum), Estimated Lender Profit
> (sum)
>
> DataFrame: (Grouped) Date Approved, (Aggregated) Loan Number (count)
>
> Plot: Scatter, Date Approved (x), Loan Number (count) (y) for Selected
> Range
>
> DataFrame: (Grouped) Date Approved, (Aggregated) Count Each State
> Column on Date
>
> Plot: Scatter, Date Approved (x), State Columns (count) (y) for
> Selected Range based on Data Available.
>
> **<u>process_checks.ipynb</u> –** Comparison Check of File Size,
> Columns (Names/Count), Row Counts, dtypes for all main script process
> inputs/outputs for 2021 and 2023 files. Includes overview of: Raw
> input files, ppp_pipe and ppp_pipe23, ppp_hash and ppp_hashSort,
> ppp_hpgf, ppp_geo, ppp_geo_fips.
>
> **<u>raw_compare.ipynb</u> –** Comparison of Raw 2021 and Raw 2023
> file updates, changes, additions, deletions.
>
> **<u>update_compare.ipynb</u> -** Addresses in Raw 2023 file compared
> to addresses in final 2023 output file.
>
> **<u>null_updates.ipynb</u> –** Outputting of files for select columns
> containing Null values.
