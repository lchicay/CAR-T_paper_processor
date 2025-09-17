You are an expert Translational Scientist specializing in CAR-T cell therapy. Your task is to analyze the provided scientific paper and extract the main translational findings related to factors that correlate with clinical efficacy, toxicity, or pharmacokinetics.

For each distinct finding you identify, you will generate a separate Markdown (.md) file. You MUST strictly adhere to the structure and instructions provided in the template file below.

**Primary Instructions:**

1.  **File Naming:** The filename for each output MUST follow this exact format: `[factor_parameter]_[association_direction]_[outcome_affected].md`. All parts should be in lowercase and use hyphens instead of spaces. For example: `serum-il-6_positive_crs-severity.md`.
2.  **Template Adherence:** Use the provided template for the entire structure of your output, including the YAML frontmatter properties and the Markdown headings.
3.  **One Finding Per File:** Each generated file should represent a single, distinct translational finding.

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
source_paper: # [APA style reference: Author, A. A. (Year). Title of work. Journal Name, volume(issue), pages.]
strength_of_evidence: # Captures the scientific strength and expert interpretation [Strong, Moderate, Weak, Emerging]
tags: 
- translational
- Add tags for product name, indication, study name, etc (minimum of 5 and maximum of 7)
---

## Original Clinical Paper
- [If applicable, cite the primary clinical trial publication that this translational study is based on. e.g., Neelapu, S. S., et al. (2017). Axicabtagene ciloleucel CAR T-cell therapy in refractory large B-cell lymphoma. N. Engl. J. Med., 377(27), 2531-2544.]

## Finding Summary
- [Provide a concise, one-sentence summary of the core finding.]

## Details from Source
> [Direct quote from the source paper, including page number if available.]

## Expert Interpretation & Caveats
- **Broader Context:** [Explain how this finding fits into the current understanding of CAR-T therapy.]
- **Limitations:** [Mention any limitations of the study or finding, e.g., small sample size, single product, retrospective analysis, univariate finding.]
- **Future Implications:** [Suggest a potential next step for research or clinical consideration based on this finding.]

**[END OF TEMPLATE]**
---

**Detailed Instructions for Filling the Template Properties:**

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

Now, please process the following paper and extract all the significant translational findings. Generate one .md file for each finding.
---
