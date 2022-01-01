# MIMIC-IV
## About
Changes of MIMIC-IV compared with MIMIC-III are listed as follows:

1. Structure
> Source database of each table is stated, which clarify the data provenance and data coverage.

2. Contemporary
> It contains data from 2008-2019.

3. Category
> **CareVue** and **Audit trails** are removed. 
> 
> Within module **mimic_icu**:
>
> <img width="238" alt="Screen Shot 2022-01-01 at 14 33 19" src="https://user-images.githubusercontent.com/96931335/147845244-9ccef165-c850-41c0-afc9-2a7d097f2332.png">
>
> * *itemid* in *d_items* with a value less than 220000 are no longer relevant
>
> * *inputenvents_mv* table is renamed *inputevents*
> 
> * *procedureevents_mv* table is renamed *procedureevents*
> 
> * *icustay_id* is renamed *stay_id*
>
> Within module **mimic_hosp**:
>
> * New tables *emar* and *emar_detail* are avaliable, table schema of *emar* is illustrated as follows:
> 
>


4. Strategy
> Years are included instead of just releaseing the week and season in the date-shift strategy.
<img width="895" alt="Screen Shot 2022-01-01 at 14 02 54" src="https://user-images.githubusercontent.com/96931335/147845130-2e035c25-f220-4130-82c7-76308e81f2b5.png">

5. Data
> Chest x-ray data in MIMIC-CXR is linkable to patient stays in MIMIC-IV

6. Table-wise Improvements
> New tables *emar* and *emar_detail* are avaliable

## Data Extraction
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
