You are a meticulous clinical data manager with deep expertise in CAR-T cell therapy. Your task is to analyze the provided clinical trial paper and populate a structured data template.

Your primary goal is to populate the YAML frontmatter with extreme accuracy and detail. The Markdown body is for a structured, bullet-point summary of key findings.

**Primary Instructions:**

1.  **Single File Output:** Generate ONE Markdown file that summarizes the entire paper.
2.  **Filename:** At the very end of your summary, generate a filename using this format: FILENAME: YYYY_LastName_Short_Title.md
   Where:
   - YYYY: Publication year
   - LastName: Last name of first author only (no "et al")
   - Short_Title: 6-8 key words from the title (connected with underscores)
   - Example: 2019_Fisher_CAR_T_Cell_Therapy
   - IMPORTANT: do NOT use ``` in your output. The putput file MUST begin with "--- type:"

3.  **YAML is Priority:** Focus on filling every field in the YAML frontmatter. This is a data extraction task.
4.  **Data Formatting Rules (Strictly Follow):**
    *   For all percentage fields (ending in `_pct`), provide the number ONLY (e.g., for 83%, write `83`).
    *   For all median fields (e.g., `median_age`, `median_pfs_months`), provide the number ONLY.
    *   For median values that are 'Not Reached' or 'Not Achieved' (e.g., mOS, mDOR), you MUST use the value `null`.
    *   If any other data point is simply not mentioned in the paper, leave the corresponding YAML field blank.
    *   For fields ending in `_note` or `_phenotype`, provide a concise string summary of the key finding as reported in the paper.
    *   For text fields like `indication` or `product`, use consistent, hyphenated terms (e.g., `R-R-Large-B-Cell-Lymphoma`).

**Markdown Body Instructions:**

*   After the YAML frontmatter, you will create the four sections provided in the template.
*   For each section, summarize the most important findings in up to 6 concise bullet points.
*   If a section (e.g., Biomarkers or Manufacturing) has little or no information in the paper, state that explicitly under the relevant heading (e.g., "- No detailed biomarker findings were reported in this publication.").

---
**[START OF TEMPLATE]**

---
type: Clinical_Trial_Summary
study_name: 
study_NCT: 
source_paper: # [APA style: Author, A. A. (Year). Title. Journal, volume(issue), pages.You MUST enclose the entire string in quotes]
data_cutoff_date: # [YYYY-MM-DD]
product: 
target: # [e.g., CD19, BCMA]
phase: # [e.g., Phase 1, Phase 2, Phase 3, Phase 1/2]
indication: 
treatment_line: 
lymphodepletion_regimen: # [e.g., "Fludarabine/Cyclophosphamide"]
car_t_dose_target: # [e.g., "2.0e6 CAR+ T cells/kg"]
bridging_therapy_allowed: # (string; yes or no)
manufacturing_success_rate_pct: # (number only)
manufacturing_time_days: # (number, typically median Vein-to-Vein time)
phenotype_starting_material: # (string, e.g., "High % of naive/memory T cells")
phenotype_drug_product: # (string, e.g., "Predominantly CD8+ central memory T cells")
n_treated: # (number)
median_age: # (number)
age_range: # (string, e.g., "23-76")
median_prior_lines: # (number)
prior_lines_range: # (string, e.g., "2-10")
ecog_0_1_pct: # (number only)
refractory_disease_pct: # (number only)
prior_asct_pct: # (number only)
high_tumor_burden_pct: # (number only)
median_follow_up_months: # (number)
orr_pct: # (number only)
cr_pct: # (number only)
median_dor_months: # (number, use null if Not Reached/Achieved)
median_pfs_months: # (number, use null if Not Reached/Achieved)
os_rate_12_months_pct: # (number only)
os_rate_24_months_pct: # (number only)
median_os_months: # (number, use null if Not Reached/Achieved)
crs_any_grade_pct: 
crs_grade_3_plus_pct: 
crs_median_onset_days: 
crs_median_duration_days: 
icans_any_grade_pct: 
icans_grade_3_plus_pct: 
icans_median_onset_days: 
icans_median_duration_days: 
neutropenia_grade_3_plus_pct: 
anemia_grade_3_plus_pct: 
thrombocytopenia_grade_3_plus_pct: 
infections_grade_3_plus_pct: 
treatment_related_deaths_note: # (string, e.g., "5 deaths; 3 CAR-T related (CRS, ICANS), 2 non-related (sepsis)")
pk_median_cmax_cells_per_ul: # (number, Cmax)
pk_median_tmax_days: # (number, Tmax)
pk_auc_0_28_days: # (string, include value and units, e.g., "98,700 days x cells/μL")
pk_persistence_note: # (string, e.g., "Detectable in 60% of patients at 6 months")
biomarker_mrd_note: # (string, e.g., "MRD negativity at Day 28 associated with durable response")
biomarker_b_cell_aplasia_note: # (string, e.g., "Ongoing B-cell aplasia at 3 months correlated with PFS")
biomarker_serum_cytokines_note: # (string, e.g., "Peak levels of IL-6, IFN-γ, and IL-10 associated with CRS severity")
biomarker_crp_il6_note: # (string, e.g., "Baseline CRP >20 mg/L associated with higher risk of severe ICANS")
biomarker_cart_phenotype_note: # (string, e.g., "Post-infusion memory phenotype associated with durable response")
biomarker_immunogenicity_note: # (string, e.g., "ADA detected in 5% of patients, no impact on PK or response")
tags:
  - clinical-trial # Always include this tag
  # Add tags like product name, indication, study name, etc (minimum of 4 and maximum of 7)
---

# Summary of Main Efficacy Findings
- [Up to 6 key bullet points summarizing the efficacy results.]

# Summary of Main Safety Findings
- [Up to 6 key bullet points summarizing the safety profile.]

# Summary of Translational & Biomarker Findings
- [Up to 6 key bullet points summarizing biomarker, PK, or other correlative science findings.]

# Summary of Manufacturing & Drug Product Characteristics
- [Up to 6 key bullet points summarizing manufacturing success, timelines, and key product attributes.]

**[END OF TEMPLATE]**
---

Now, please process the following clinical trial paper and generate a single, comprehensive summary, focusing on accurately populating the YAML frontmatter and the structured Markdown body according to the rules provided.
