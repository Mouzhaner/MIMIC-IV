# MIMIC-IV
## About
Changes of MIMIC-IV compared with MIMIC-III are listed as follows:

#### Structure
> Source database of each table is stated, which clarify the data provenance and data coverage.

#### Contemporary
> It contains data from 2008-2019.

#### Category
> 1. **CareVue** and **Audit trails** are removed. 
> 
> 2. Within module **mimic_icu**:
>
>    <img width="238" alt="Screen Shot 2022-01-01 at 14 33 19" src="https://user-images.githubusercontent.com/96931335/147845244-9ccef165-c850-41c0-afc9-2a7d097f2332.png">
>
>   * *itemid* in *d_items* with a value less than 220000 are no longer relevant
>
>   * *inputenvents_mv* table is renamed *inputevents*
> 
>   * *procedureevents_mv* table is renamed *procedureevents*
> 
>   * *icustay_id* is renamed *stay_id*
>
> 3. Within module **mimic_hosp**:
>
>   * *emar* and *emar_detail*
> 
>     New tables *emar* and *emar_detail* are avaliable, sourced from the relatively newly installed electronic Medicine Administration Record (eMAR) system.
>     Bedside staff will scan barcodes for each individual formulary unit of a medication when administering it. This allows for a granular, high resolution record
>     of when a medication was given. Table schema of *emar* is illustrated as follows:
>    
>       <img width="308" alt="Screen Shot 2022-01-01 at 14 45 25" src="https://user-images.githubusercontent.com/96931335/147845503-8ed8d44c-c8d1-4481-972f-44215c7cb276.png">
>
>    * *labevents*
>    
>      * Reference ranges, i.e. *ref_range_lower* and *ref_range_upper* are now avaliable
>     
>      * *specimen_id* allows users to group all measurements made from a single specimen
>      
>      * *priority* indicates the priority level of the laboratory measure, i.e. STAT / ROUTINE
>
>        <img width="868" alt="Screen Shot 2022-01-01 at 15 06 12" src="https://user-images.githubusercontent.com/96931335/147845727-33c0293e-6703-4738-afbf-7cb4472ba00c.png">
>      
>        <img width="84" alt="Screen Shot 2022-01-01 at 15 47 00" src="https://user-images.githubusercontent.com/96931335/147846391-a8ce78ea-506a-4d63-a3a9-c7d21984d7dd.png">
>        <img width="205" alt="Screen Shot 2022-01-01 at 15 47 09" src="https://user-images.githubusercontent.com/96931335/147846393-b5d8d266-00e0-48d8-900e-99490b9f4186.png">
>        <img width="67" alt="Screen Shot 2022-01-01 at 15 48 47" src="https://user-images.githubusercontent.com/96931335/147846417-0d8d6fe9-cf10-4b98-b759-393a5d69172f.png">





#### Strategy
> Years are included instead of just releaseing the week and season in the date-shift strategy.
  <img width="895" alt="Screen Shot 2022-01-01 at 14 02 54" src="https://user-images.githubusercontent.com/96931335/147845130-2e035c25-f220-4130-82c7-76308e81f2b5.png">

#### Data
> Chest x-ray data in MIMIC-CXR is linkable to patient stays in MIMIC-IV


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
