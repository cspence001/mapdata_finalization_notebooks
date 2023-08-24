# mapdata_finalization_notebooks
geocoding api, hashing, labeling<br>


<h6>
file_update.ipynb - public database updating <br><br>

main_HASHING.ipynb - hash sequencing variables <br>

main_concat.ipynb - finalization of state database files <br>

main_label_geo.ipynb - main geocoding <br>

main_label_pipe.ipynb - main preliminary labeling, NAICS, range groups </h6>

Repo: **mapdata_finalization_notebooks**

**Processes Raw Data obtained from SBA Public Data Directory for the
release of PPP Loan Data in 2021 and 2023.**

**Scripts:**

> **[main_label_pipe.ipynb]{.underline} -** processes raw data through
> pipeline of cleaning, formatting, and integrating associated data
> sources to expand on given database.
>
> **[main_HASHING.ipynb]{.underline} -** creates HASHcode column for
> dataframe with variables for Industry, Industry Subsector, Loan Range,
> Job Range, Business Type, Business Age, and PPP/PPS program.
>
> **[main_concat.ipynb]{.underline} --** combines final outputs of
> main_label_pipe, main_hashing, and Geo processed FIPS files for
> finalized output to be used in state aggregation.

**Updates/comparisons**

> **[column_value_checks.ipynb]{.underline} --** Exploratory Data Post
> Pipe process:
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
> **[process_checks.ipynb]{.underline} --** Comparison Check of File
> Size, Columns (Names/Count), Row Counts, dtypes for all main script
> process inputs/outputs for 2021 and 2023 files. Includes overview of:
> Raw input files, ppp_pipe and ppp_pipe23, ppp_hash and ppp_hashSort,
> ppp_hpgf, ppp_geo, ppp_geo_fips.
>
> **[raw_compare.ipynb]{.underline} --** Comparison of Raw 2021 and Raw
> 2023 file updates, changes, additions, deletions.
>
> **[update_compare.ipynb]{.underline} -** Addresses in Raw 2023 file
> compared to addresses in final 2023 output file.
>
> **[null_updates.ipynb]{.underline} --** Outputting of files for select
> columns containing Null values.

**Repo: mapdata_fips_aggregation**

**Processes location coordinates and FIPS codes for 2021 and 2023 PPP
Loan Data.**

**Scripts:**

> **census_geocoder --** each state file is parsed in a separate
> notebook using this script to obtain Latitude and Longitude
> coordinates when Google Data Limit is reached as well as FIPS codes
> from geo.census.gov, parses using one line address form:
>
> <https://geocoding.geo.census.gov/geocoder/geographies/onelineaddress?form>
>
> 21
>
> **[census_geocoderST.ipynb]{.underline}** - separate coordinate + FIPS
> processing for (14) States/Territories using 2021 data.
>
> **selenium_fips -** each state file is parsed in a separate notebook
> using this script to obtain FIPS codes for previously obtained
> Latitude and Longitude coordinates from geo.census.gov, parses using
> geography coordinates form:
>
> <https://geocoding.geo.census.gov/geocoder/geographies/coordinates?form>
>
> 21
>
> **[selenium_census_script_fipscheck_ST.ipynb]{.underline}** --
> separate FIPS processing for (56) U.S. States/Territories using 2021
> data.
>
> 23
>
> **[selenium_census_script_fipscheck_ST23.ipynb]{.underline}** -
> separate FIPS processing for (52) U.S. States/Territories using 2023
> data. FIPS data was obtained from 2021 data for all Loan Numbers
> matching 2023 data, and 2023 update was not needed for remaining
> States/Territories (4).
>
> **[selenium_census_script_fipscheck\_]{.underline}****[23.ipynb]{.underline}**
> -- FIPS processing for states Loans that required manual input/update
> of address and/or latitude, longitude fields in 2023 data.
>
> **[script_combine_fips21.ipynb]{.underline}** -- combines all FIPS
> processed state files for 2021 data.
>
> **[script_combine_fips23.ipynb]{.underline}** - combines all FIPS
> processed state files for 2023 data, merges 2021 FIPS processed data
> file for Loan Numbers included in 2023 data
>
> **[script_fipssplit\_]{.underline}****[23.ipynb]{.underline}** --
> splits 2023 data into separate state files after 2021 merges to be
> processed for FIPS separately and re-combined.
>
> google_geocoder - **states are processed at 20k limit intervals using
> Google API geocoder to obtain coordinates for each business address.**
>
> **[geopipe.ipynb]{.underline}** - processes 2021 data for latitude and
> longitude. Each state is manually updated in script.
>
> **[geopipe23.ipynb]{.underline}** - processes 2023 data for latitude
> and longitude that was not included in previously processed 2021 data.
> Each state is manually updated in script.
>
> **[combine_geostates.ipynb]{.underline}** - combines 2021 Geo
> processed state files into one main file if state was processed
> separately.
>
> **[geopipe_FL.ipynb]{.underline}** - separately processed state file
> for repair/verification of coordinate fields. Re-combined to main in
> combine_geostates.

**Repo: mapdata_state_aggregation**

**Aggregates associated State Shapefiles with finalized data output for
PPP Loan Data.**

> **state_aggregation**
>
> **[ST_FIPS_aggregation.ipynb]{.underline} - State (56) Shapefile
> aggregation of State, County, Blockgroup, Block, and geometry Point
> pairing. GeoDataFrame JSON conversion.**
