# MIMIC-IV
## About
Changes of MIMIC-IV from MIMIC-III are listed as follows:
1.Structure
>source database of each table is stated, which clarify the data provenance and data coverage.
2.Contemporary
>contains data from 2008-2019
3.Category
* CareVue is no more
>itemid in d_items with a value less than 220000 are no longer relevant
>inputenvents_mv table is renamed inputevents
>procedureevents_mv table is renamed procedureevents
* icustay_id is renamed stay_id



## Data extraction
The data extraction steps are run by BigQuery and generates the final view of the data concerning the following diseases:
* tuberculosis
* sepsis
* bacterial infection
* HIV infection
* hepatitis
* viral infection
* cancer of head and neck
* Hodgkin's disease
* leukemia
* diabetes mellitus without complication
* nutritional deficiency
* pulmonary heart disease 

### TODO:
* generate disease IDs
* generate patient IDs
* extract detailed info including specific feautures and survival conditions

### Details
#### disease IDs
>This can be found in 'Reference_table MIMIC-IV' excel

#### patient IDs
>This can be found in 'Reference_table MIMIC-IV' excel
