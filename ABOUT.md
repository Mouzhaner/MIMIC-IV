# MIMIC-IV: About
Changes of MIMIC-IV compared with MIMIC-III are listed as follows:

### Structure
Source database of each table is stated, which clarify the data provenance and data coverage.

### Contemporary
It contains data from 2008-2019.

### Category
#### Table-wise improvements over MIMIC-III & Changed module components
1. *CareVue* and *Audit trails* are removed. 
> 
2. Within module *mimic_icu*:

    <img width="238" alt="Screen Shot 2022-01-01 at 14 33 19" src="https://user-images.githubusercontent.com/96931335/147845244-9ccef165-c850-41c0-afc9-2a7d097f2332.png">
    <img width="58" alt="Screen Shot 2022-01-01 at 16 39 18" src="https://user-images.githubusercontent.com/96931335/147847123-40f2cb28-ece6-49d8-a937-03efcb21dfb3.png">

>
>   * `itemid` in *d_items* with a value less than 220000 are no longer relevant
>
>   * `inputenvents_mv` table is renamed `inputevents`
> 
>   * `procedureevents_mv` table is renamed `procedureevents`
> 
>   * `icustay_id` is renamed `stay_id`
>
3. Within module *mimic_hosp*:
>
>    * *emar* and *emar_detail*
>
>      New tables `emar` and `emar_detail` are avaliable, sourced from the relatively newly installed electronic Medicine Administration Record
>      (eMAR) system. Bedside staff will scan barcodes for each individual formulary unit of a medication when administering it. This allows for a
>      granular, high resolution record of when a medication was given. Table schema of `emar` is illustrated as follows:
>      
>         <img width="308" alt="Screen Shot 2022-01-01 at 14 45 25" src="https://user-images.githubusercontent.com/96931335/147845503-8ed8d44c-c8d1-4481-972f-44215c7cb276.png">
>    * *microbiologyevents*
> 
>      Now contains the name of the test performed, i.e. `test_name`
>     
>         <img width="291" alt="Screen Shot 2022-01-01 at 16 00 53" src="https://user-images.githubusercontent.com/96931335/147846569-198cae2d-7093-40e5-986f-32855025451e.png">         
>
>    * *labevents*
>    
>      * reference ranges `ref_range_lower` and `ref_range_upper` are now avaliable
>     
>      * a specimen identifier `specimen_id` allows users to group all measurements made from a single specimen
>      
>      * `priority` indicates the priority level of the laboratory measure: STAT / ROUTINE
>      
>        <img width="84" alt="Screen Shot 2022-01-01 at 15 47 00" src="https://user-images.githubusercontent.com/96931335/147846391-a8ce78ea-506a-4d63-a3a9-c7d21984d7dd.png">
>        <img width="205" alt="Screen Shot 2022-01-01 at 15 47 09" src="https://user-images.githubusercontent.com/96931335/147846393-b5d8d266-00e0-48d8-900e-99490b9f4186.png">
>        <img width="67" alt="Screen Shot 2022-01-01 at 15 48 47" src="https://user-images.githubusercontent.com/96931335/147846417-0d8d6fe9-cf10-4b98-b759-393a5d69172f.png">
>
>    * *prescriptions*
>    
>      * using `starttime` and `stoptime` to replace `startdate` and `enddate`, which shows both the time and date
>      
>         <img width="271" alt="Screen Shot 2022-01-01 at 16 43 28" src="https://user-images.githubusercontent.com/96931335/147847205-186c4ece-d5ad-4820-b70e-46c1a88a3bf0.png">
>       
>      * `drug_name_generic`, `drug_name_poe` and `fromulary_drug_cd` are removed
>      
>      * new columns includes `pharmacy_id`, `form_rx` and `doses_per_24_hrs`
>      
>        `pharmacy_id` - to link to the pharmacy table which has additional information about the prescription
>        
>        `doses_per_24_hrs`provides the number of doses per 24 hours prescribed by this row
>        
>        <img width="109" alt="Screen Shot 2022-01-01 at 16 58 23" src="https://user-images.githubusercontent.com/96931335/147847410-bf38e4b3-a8c0-4bf3-9911-0272f4ff5640.png"><img width="60" alt="Screen Shot 2022-01-01 at 16 58 11" src="https://user-images.githubusercontent.com/96931335/147847414-62c2d153-c4bd-4ab2-858c-a455164434cd.png"><img width="80" alt="Screen Shot 2022-01-01 at 16 58 45" src="https://user-images.githubusercontent.com/96931335/147847411-636fc5e9-761c-4c31-855f-8d78d776ba41.png">










### Strategy
Years are included instead of just releaseing the week and season in the date-shift strategy.
> 
<img width="273" alt="Screen Shot 2022-01-01 at 16 17 09" src="https://user-images.githubusercontent.com/96931335/147846784-a9f01423-7026-4bc5-904c-931651cb3ea5.png">

### Data
Chest x-ray data in MIMIC-CXR is linkable to patient stays in MIMIC-IV.


# Data Extraction
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

## TODO:
* generate disease IDs
* generate patient IDs
* extract detailed info including specific feautures and survival conditions

## Details
### disease IDs
>This can be found in 'Reference_table MIMIC-IV' excel

### patient IDs
>This can be found in 'Reference_table MIMIC-IV' excel
