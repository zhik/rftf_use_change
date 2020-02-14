# Religious Facilities Task Force - Use Change Project

BetaNYC is with working NYU Urban Planning & MBPO Land Use Unit to find and classify Religious Facilities. The outcome of the [Religious Facilities Task Force](https://www.manhattanbp.nyc.gov/rftf/) is to craft a guide book and policy to protect/preserve their religious facilities or congregation from developments or other issues.

This repo contains jupyter notebooks and their outputs.

We are using 2010 - 2020 [PLUTO](https://www1.nyc.gov/site/planning/data-maps/open-data/dwn-pluto-mappluto.page) data to analyse use change and other various variables to:

- Understand and identify trends, common problems, and conditions to generate meaningful observations information an existing conditions memo and introduction material for an action book.
- Identify especially challenging or interesting properties or areas worthy of site visits and case studies.

---

### 1. Prepare PLUTO.ipynb

Prepare all versions of PLUTO into a standard format bbl format.

### 2. Combine Years.ipynb

Get BldgClass,LotArea,BldgArea,HistDist,Landmark, OwnerName from all years; then merge on bbl with the prefix of year (e.g. 2019_histdist)

Then join to lastest PLUTO to get cd, council, address, xcoord, ycoord

Output: `./processed_data/filtered_m.csv`

### 3. Fetch DOB data.ipynb

Using [DOB Permit Issuance](https://data.cityofnewyork.us/Housing-Development/DOB-Permit-Issuance/ipu4-2q9a/data) dataset, fetch all A1, A2, A3 (Alterations), NB (New building), DM (Demolition) for the BBL. Then create columns dob_A1, dob_A2, dob_A3, dob_NB, dob_DM, dob_ALL with the counts for all the types.

Output: `./processed_data/merged_step3.csv`

### Analysis - PLUTO Build and UnBuilt

Calculate approx Unbuilt FAR using allowed residfar, commfar, facilfar and builtfar (existing FAR)

Output: `./processed_data/merged_step4.csv`

### Analysis - Adjacent to vacant lots

Merge an analysis on QGIS to identify RF lots adjacent/touching ‘vacant lots’ and ‘soft sites’

Output: `./processed_data/merged_step5.csv`

### Analysis - Average Lot Area

Get of Lot Area outside the percentile 10, 90 (outliners) for each of the city council districts.

Output: `./processed_data/merged_step6.csv`
