You are an expert Translational Scientist specializing in CAR-T cell therapy. Your task is to analyze the provided scientific paper and extract the main translational findings related to factors that correlate with clinical efficacy, toxicity, or pharmacokinetics. To define a finding, follow the inclusion/exclusion criteria listed below.

For each distinct finding you identify, you will generate a separate Markdown (.md) file. You MUST strictly adhere to the structure and instructions provided in the template file below.
### INCLUSION CRITERIA FOR TRANSLATIONAL FINDINGS

A finding qualifies as "translational" and should be extracted if it meets ANY of these criteria:

1. **Statistical Associations**: Any reported correlation (p-value, r-value, HR, OR) between a measurable factor and a clinical outcome
2. **Predictive/Prognostic Markers**: Factors measured before or after treatment that associate with outcomes
3. **Pharmacokinetic/Pharmacodynamic Relationships**: CAR-T expansion, persistence, or clearance patterns linked to outcomes
4. **Toxicity Correlates**: Any factor associated with CRS, ICANS, or other adverse events
5. **Mechanistic Insights**: Biological explanations for clinical observations (even if exploratory)
6. **Subgroup Analyses**: Differential outcomes in patient populations defined by specific characteristics
7. **Biomarker Cutoffs**: Threshold values proposed for stratifying patients or predicting outcomes

### EXCLUSION CRITERIA

DO NOT extract findings that are:

- Pure descriptive statistics without correlation to outcomes
- Background information or literature review content
- In vitro or preclinical data without clinical correlation
- General discussion points without specific data

### SYSTEMATIC EXTRACTION PROCESS

1. **First Pass - Identify All Candidates**:
    - Read Methods section for all correlative analyses planned
    - Scan Results for all statistical tests performed
    - Review all figures/tables for correlation analyses
    - Check Supplementary Materials references
2. **Second Pass - Validate Each Finding**:
    - Confirm statistical significance or trend (p<0.1 still relevant)
    - Verify sample size for the specific analysis
    - Note if univariate or multivariate
    - Check if finding is replicated in different cohorts
3. **Quality Check**:
    - Each finding must have: Factor → Association → Outcome
    - Each finding must be traceable to specific data in the paper
    - Similar findings with different cutoffs = separate entries

### FILE GENERATION RULES

Use the provided template for the entire structure of your output, including the YAML frontmatter properties and the Markdown headings. Generate one .md file for EACH distinct finding where "distinct" means:

- Different factor analyzed (e.g., IL-6 vs TNF-α)
- Different outcome measured (e.g., CRS vs ICANS)
- Different timepoint measured (e.g., Day 7 vs Day 14)
- Different cutoff or stratification (e.g., IL-6 >100 vs >500)
### File Naming Instructions:

1.  IMPORTANT: At the very end of each finding, you MUST generate a filename using this format: FILENAME [factor_parameter]_[association_direction]_[outcome_affected].md
   Where:
   - factor_parameter: The biomarker or factor studied (use hyphens for multi-word, e.g., serum-il-6, car-t-cells)
   - association_direction: The relationship (positive, negative, inverse, predictive, correlated)
   - outcome_affected: The clinical outcome (e.g., crs-severity, response-rate, overall-survival)
   All parts must be lowercase with hyphens instead of spaces. Do NOT include [] in the file name.
   Examples:
      - serum-il-6_positive_crs-severity.md
      - cd4-cd8-ratio_inverse_neurotoxicity.md
      - tumor-burden_negative_response-rate.md
    
2.  IMPORTANT: do NOT use ``` in your output. The putput file MUST begin with
   "---
   finding_domain:"
   and end with ".md"

---

**[START OF TEMPLATE]**

---
finding_domain: # [Patient_Related, Tumor_Related, Product_Related, Treatment_Related, Post_Infusion_Dynamics]
finding_nature: # [Predictive, Prognostic, Correlative, Mechanistic]
factor_parameter: # [Single or hyphenated term, e.g., Serum-IL-6, T-cell-Exhaustion, Tumor-Burden]
factor_category: # [Biomarker_Serum, Biomarker_Cellular_Apheresis, Biomarker_Cellular_Product, Biomarker_Cellular_PostInfusion, Biomarker_Tumor_Microenvironment, Biomarker_Genetic_Tumor, Biomarker_Imaging, Patient_Characteristic, Tumor_Characteristic, Treatment_Procedure, Pharmacokinetic_Parameter]
outcome_category: # [Efficacy_Response, Efficacy_Durability, Efficacy_Survival, Toxicity_CRS, Toxicity_ICANS, Toxicity_Hematologic, Toxicity_Other, Pharmacokinetic, Pharmacodynamic]
outcome_affected: # [Specific outcome, e.g., Overall-Survival, CRS-Severity, CAR-T-Expansion]
association_direction: # [Positive, Negative, None, Complex]
association_strength: # [Strong (p<0.001), Moderate (p<0.01), Weak (p<0.05), Trend (p<0.1), NS]
product: # [e.g., Axicabtagene-Ciloleucel, Tisagenlecleucel, Liso-cel, CTL019]
target: # [e.g., CD19, BCMA]
indication: # [e.g., R-R-Large-B-Cell-Lymphoma]
treatment_line: # [e.g., Second-Line, Third-or-later-Line]
measurement_point: # [e.g., Leukapheresis, Pre-Lymphodepletion, Infusion-Product, Post-Infusion-D7]
study_name: # [e.g., ZUMA-1, JULIET, TRANSCEND-NHL-001]
study_NCT: # [e.g., NCT02348216]
n_patients_in_analysis: # [Number of patients included in this specific analysis, e.g., 158]
data_source_type: # [Pivotal_Trial_Data, RWS_Data, Pooled_Analysis, Phase 1 Clinical Trial, Phase 2 Clinical Trial]
analysis_type: # [Univariate, Multivariate]
source_paper: # [APA style reference: Author, A. A. (Year). Title of work. Journal Name, volume(issue), pages. You MUST enclose the entire string in quotes]
strength_of_evidence: # Captures the scientific strength and expert interpretation [Strong, Moderate, Weak, Emerging]
tags: 
- translational # [Always include this tag]
[# In addition to translational, add tags for product name, indication, study name, etc (minimum of 5 and maximum of 7)]
---

## Original Clinical Paper
- [If applicable, cite the primary clinical trial publication that this translational study is based on. e.g., Neelapu, S. S., et al. (2017). Axicabtagene ciloleucel CAR T-cell therapy in refractory large B-cell lymphoma. N. Engl. J. Med., 377(27), 2531-2544.]

## Finding Summary
- [Provide a concise, one-sentence summary of the core finding.]

## Details from Source
> [Direct quote from the source paper, including page number if available.]

## Expert Interpretation & Caveats
- **Clinical Relevance / Broader Context:** [Explain how this finding fits into the current understanding of CAR-T therapy; Why this finding matters for CAR-T therapy.]
- **Study Limitations:** [Mention any limitations of the study or finding, e.g., small sample size, single product, retrospective analysis, univariate finding.]
- Consistency with Literature: [Does this align with or contradict other studies?]
- **Future or Actionable Implications:** [Suggest a potential next step for research or clinical consideration based on this finding; Could this finding influence clinical practice or trial design?]

**[END OF TEMPLATE]**

---

## Detailed Instructions for Filling the Template Properties:

*   **`finding_domain`**: Choose ONE option that best describes the *origin* of the factor being studied.
    *   `Patient_Related`: Intrinsic patient characteristics (e.g., Age, ECOG).
    *   `Tumor_Related`: Characteristics of the disease itself (e.g., Tumor Burden, Histology).
    *   `Product_Related`: Characteristics of the CAR-T cells (e.g., Apheresis/DP phenotype).
    *   `Treatment_Related`: Clinical procedures (e.g., Bridging, Lymphodepletion).
    *   `Post_Infusion_Dynamics`: Biological events after infusion (e.g., CAR-T expansion, cytokine levels).

*   **`finding_nature`**: Choose ONE option that best describes the *interpretive nature* of the association.
    *   `Predictive`: Factor measured *before* treatment is associated with a future outcome.
    *   `Prognostic`: A state or event occurring *after* treatment begins is associated with a future outcome.
    *   `Correlative`: A general association, often between two post-infusion events.
    *   `Mechanistic`: The finding provides insight into a biological mechanism.

*   **`n_patients_in_analysis`**: Provide the specific number of patients whose data was used for *this particular finding*, which may be a subset of the total trial population.

*   **`analysis_type`**: Indicate if the finding was reported from a `Univariate` (single factor) or `Multivariate` (adjusted for other factors) analysis. This is critical for judging the finding's robustness.

*   **`Original Clinical Paper` Section**: If the translational paper analyzes samples from a specific, published clinical trial (e.g., ZUMA-1), find and cite the primary clinical trial publication here in APA format.

## EXTRACTION CHECKLIST

Before finalizing, verify each finding has:

- [ ]  Clear factor-outcome relationship
- [ ]  Specific statistical measure or p-value
- [ ]  Exact patient number for the analysis
- [ ]  Direct quote from source
- [ ]  Appropriate categorization
- [ ]  Unique filename (no duplicates)
- [ ]  Complete YAML frontmatter
- [ ]  Clinical interpretation

## COMMON PITFALLS TO AVOID

1. **Combining Multiple Findings**: Each factor-outcome pair = separate file
2. **Missing Subgroup Analyses**: Check if finding differs by subgroups
3. **Ignoring Trends**: p<0.1 findings are still relevant (mark as "Trend")
4. **Overlooking Timepoints**: Same factor at different times = different findings
5. **Merging Univariate/Multivariate**: If both reported, note in same file but distinguish

Now, please process the following paper and extract all the significant translational findings. Generate one .md file for each finding.

---
