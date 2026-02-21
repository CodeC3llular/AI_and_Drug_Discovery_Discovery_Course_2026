# AI-in-Drug-Discovery-Couse-2026-resubmission
QSAR Data Curation for EGFR Target - Assignment 2
# AI and Drug Discovery Course 2026

## Assignment 2: QSAR Data Curation Using ChEMBL

**Student:** Michelle Mupanduki 
**Course:** AI and Biotechnology/Bioinformatics  
**Date:** January 2026

---

##  Assignment Overview

This repository contains the QSAR data curation workflow for Assignment 2 of the AI and Drug Discovery course. The objective is to retrieve, process, and curate bioactivity data from the ChEMBL database for subsequent QSAR modeling.

---

##  Selected Target

**Target Name:** Epidermal Growth Factor Receptor (EGFR)  
**ChEMBL ID:** CHEMBL203  
**Organism:** Homo sapiens  
**Target Type:** Single protein  

**Clinical Relevance:**
- **Primary Diseases:** Non-small cell lung cancer (NSCLC), glioblastoma
- **Therapeutic Importance:** EGFR is a validated oncology target with multiple FDA-approved inhibitors (gefitinib, erlotinib, osimertinib)
- **Drug Discovery Value:** Well-characterized target with extensive structure-activity relationship (SAR) data

**Why EGFR was Selected:**
- Extensive bioactivity data available in ChEMBL (10,000+ compounds)
- Well-established structure-activity relationships
- Proven track record in drug development
- Diverse chemical scaffolds provide robust QSAR training set
- Clear biological relevance in oncology

---

##  Bioactivity Records

- **Initial records retrieved:** ~ 97 records
- **Final curated dataset:** ~ 83 compounds
- **Bioactivity measurement:** IC50 (nM)
- **Classification thresholds:**
  - **Active:** IC50 ≤ 1,000 nM (potent EGFR inhibitors)
  - **Intermediate:** 1,000 nM < IC50 < 10,000 nM (moderate inhibitors)
  - **Inactive:** IC50 ≥ 10,000 nM (weak or no activity)

---

##  Data Curation Workflow

### 1. **Target Selection**
- Search ChEMBL database for EGFR targets
- Select Epidermal Growth Factor Receptor (CHEMBL203) based on:
  - Large number of bioactivity records
  - High-quality IC50 data
  - Clinical and research significance

### 2. **Data Retrieval**
- Query ChEMBL web services API for IC50 bioactivity data
- Retrieve compound structures (SMILES notation)
- Extract standardized activity measurements

### 3. **Data Preprocessing**
- **Quality Control:**
  - Remove records with missing bioactivity values
  - Remove records with invalid or missing SMILES structures
  - Filter for standardized units (nM only)
  - Remove duplicate compounds (keep first occurrence)
  
- **Data Standardization:**
  - Convert all IC50 values to nanomolar (nM) units
  - Validate SMILES string integrity
  - Ensure consistent data formatting

### 4. **Bioactivity Classification**
- Classify compounds into three categories based on IC50 values:
  - **Active compounds:** Potential lead candidates (IC50 ≤ 1 μM) - 22 compounds
  - **Intermediate compounds:** Optimization candidates - 15 componds 
  - **Inactive compounds:** Used for negative training examples -46 compounds
- Create balanced dataset suitable for classification-based QSAR modeling

### 5. **Data Export**
- Save curated dataset in CSV format
- Store both raw and preprocessed data for reproducibility
- Document data provenance and curation steps

---

##  Repository Structure

```
AI_and_Drug_Discovery_Course_2026/
│
├── assignment_2_QSAR_data_curation (1).ipynb   
├── README.md                                 
├── bioactivity_raw_data (2).csv                          
└── bioactivity_preprocessed_data (2).csv                    
```

---

## Technologies Used

- **Python 3.x**
- **Libraries:**
  - `chembl_webresource_client` - ChEMBL database API access
  - `pandas` - Data manipulation and analysis
  - `numpy` - Numerical operations
- **Platform:** Google Colab (cloud-based Jupyter notebook)
- **Database:** ChEMBL

---

##  How to Use This Repository

### Prerequisites
- Google account (for Google Colab)
- Internet connection

### Steps to Reproduce

**1. Clone this repository:**
```bash
git clone https://github.com/[your-username]/AI_and_Drug_Discovery_Course_2026.git
```

**2. Open the notebook in Google Colab:**
- Go to https://colab.research.google.com/
- File → Upload notebook
- Select `assignment_2_QSAR_data_curation.ipynb`

**3. Mount Google Drive:**
- Run the first cell to connect to your Google Drive
- Authorize access when prompted

**4. Run all cells sequentially:**
- Runtime → Run all
- Or execute cells one by one with Shift+Enter

**5. Access output files:**
- Files will be saved in: `Google Drive/Colab Notebooks/data/`
- Download CSV files for further analysis

---

##  Expected Outputs

### Files Generated:
1. **`bioactivity_raw_data.csv`**
   - Raw bioactivity data directly from ChEMBL
   - Contains all retrieved records before preprocessing
   - Includes metadata and additional columns

2. **`bioactivity_preprocessed_data.csv`**
   - Cleaned and classified dataset ready for QSAR modeling
   - Contains only relevant columns:
     - `molecule_chembl_id`: Unique compound identifier
     - `canonical_smiles`: Chemical structure representation
     - `standard_value`: IC50 value in nM
     - `bioactivity_class`: Active/Intermediate/Inactive classification

### Data Quality Metrics:
- Data retention rate: ~85.6% of initial records
- All compounds have valid SMILES and standardized IC50 values
- No missing values in critical columns

---

##  Scientific Context

### EGFR in Cancer Biology
The Epidermal Growth Factor Receptor (EGFR) is a transmembrane tyrosine kinase receptor that plays a crucial role in cell proliferation, survival and differentiation. Aberrant EGFR signaling is implicated in various cancers:

- **Non-Small Cell Lung Cancer (NSCLC):** EGFR mutations found in ~15-30% of cases and higher in Asian populations 
- **Glioblastoma:** EGFR amplification occurs in ~40-50% of primary glioblastomas
- **Other cancers:** Colorectal, breast head and neck cancers

### QSAR Modeling Applications
This curated dataset enables:
- **Predictive modeling:** Estimate IC50 values for new compounds
- **Virtual screening:** Prioritize compounds for synthesis/testing
- **Lead optimization:** Identify structural features for improved potency
- **Drug repurposing:** Identify existing drugs with EGFR activity

---

##  Notes

- The number of bioactivity records may vary depending on ChEMBL database version and update date
- Data curation follows best practices for QSAR dataset preparation as outlined in scientific literature
- The curated dataset is suitable for subsequent molecular descriptor calculation and QSAR model development (Part 2 of the course)
- EGFR's extensive bioactivity data makes it an ideal target for demonstrating QSAR methodologies

---

##  References

1. **ChEMBL Database:** https://www.ebi.ac.uk/chembl/
   - Gaulton A, et al. (2017). The ChEMBL database in 2017. Nucleic Acids Res. 45(D1):D945-D954.

2. **Course Repository:** https://github.com/AI-Biotechnology-Bioinformatics/Drug_Discovery_AI_Course_2026

3. **EGFR as Drug Target:**
   - Cohen MH, et al. (2004). FDA drug approval summary: Gefitinib. Oncologist. 9(5):503-512.
   - Sharma SV, et al. (2007). Epidermal growth factor receptor mutations in lung cancer. Nat Rev Cancer. 7(3):169-181.

---

### Author

**Michelle Mupanduki**  
M.S. Biotechnology   
---

##  Contact

For questions or clarifications about this assignment, please contact through the course platform or GitHub issues.

---
