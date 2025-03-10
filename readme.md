# AMR Surveillance on FHIR

*Work in progress*

Maturity : Draft  (for disscussion with stakeholders)


A FHIR-based logical model for standardizing antimicrobial resistance (AMR) surveillance data in microbiology laboratories of human health. This model focuses on **culture-based diagnostics**, **microscopy**, and organism properties which are currently being used or will be introduced in near future. Besides, surveillance this will also facilitate the standardization of the AMR realted data at the source(EMR/EHR/LMIS at hospitals and labs). 

**Developed for** 

`National Public Health Laboratory (NPHL)` <br>
`Quality Standards and Regulatory Division(QSRD)` <br>
`Ministry of Health and Population (MoHP)`. 

Supported by 
`Fleming Fund Country Grant for Nepal (FFCGN)/FHI360` and `Group for Technical Assistant`. 

---

## Table of Contents
- [Purpose](#purpose)
- [Features](#features)
- [Structure Overview](#structure-overview)
- [Example](#example)
- [Contribution](#contributing)

---

## Purpose
To enable interoperable reporting of microbiology test results for AMR surveillance using FHIR standards. This model supports:
- Culture diagnostics (organism detection, Suspceptibility, colony count).
- Microscopy findings (morphology, staining methods).
- Classification of multidrug-resistant organisms (MDROs).
- details of resistance and microorganism (ResistanceMechanism including genes and)

---

## Features
### Core Components for Mirobiology
1. **Culture Diagnostics**
   - `Detection`: Presence/absence of microorganisms (e.g., "Gram-positive cocci").
   - `OrganismName`: SNOMED CT-coded organism names (e.g., *Escherichia coli*).
   - `CultureMethod`: Methods like "Agar plate culture."
   - `MRGN`: Multi-resistant Gram-negative classification (e.g., "3MRGN").
   - `ColonyCount`: Quantified results (e.g., `10^5 CFU/mL`).
   - `Susceptibility`: Antibiotic susceptibility profiles.

2. **Microscopy**
   - `SemiquantitativeResult`: Categories like "Few" or "Many."
   - `Morphology`: Structural features (e.g., "rod-shaped").
   - `Method`: Staining techniques (e.g., "Gram stain").

3. **Further Properties**
   - `MDROType`: ESBL, MRSA, etc.
   - `MRGNClassification`: Robert Koch Institute guidelines.
   - `ResistanceMechanism`: Genes (e.g., `blaCTX-M-15`) and mutations.

4. **DiagnosticReport**
   - Aggregates findings into a clinical report.

### Components for Subject 
1. **Patient**
    - `Pesudo-anomized identifier`
    - `birthDate`
    - `address`
    - `gender`

2. **Encounter**
    - `type`
    - `serviceProvider`
    - `serviceType`

3. **Condition**

4. **MedicationDispense**
---

## Structure Overview
```text
amr_microbiology_logical_model
├── Culture_diagnostics
│   ├── Detection
│   ├── OrganismName
│   ├── CultureMethod
│   ├── MRGN
│   ├── ColonyCount
│   └── Susceptibility
├── Microscopy
│   ├── Detection
│   ├── OrganismName
│   ├── SemiquantitativeResult
│   ├── Method
│   └── Morphology
├── Further_properties
│   ├── MDROType
│   ├── Resistance_mechanism
│   │   ├── ResistanceGene
│   │   └── ResistanceMutation
│   └── MRGNClassification
└── DiagnosticReport
```
## Example

## Contribution
>National public Health Laboratory 

>Quality Standards and Regulatory Division(QSRD)

>Prabin Raj Shakya (lead Consultant), prabinrs@gmail.com

>Rakesh Panthi(Senior SI specialist), rakeshpanthi008@gmail.com

>Subrat Gyawali (Technical Consultant), subhratmanigyawali@gmail.com

## Learning Resouces
- 📘 [**FHIR 101**](https://github.com/prabinrs/FHIR_telemed_2025)
