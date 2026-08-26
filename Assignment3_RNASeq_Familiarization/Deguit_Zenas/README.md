# RNA-Seq Data Familiarization and Quality Characterization

## Hypoxia6h_R2 — Hypoxia-Treated Endothelial Cells

**Assignment 3 | Group 2: Hypoxia**

**Student:** Deguit, Zenas Charis C.  
**NCBI SRA Run:** `SRR26073703`  
**BioProject:** `PRJNA1017894`

---

## Sample Overview

This README presents the identification, characterization, and quality assessment of the RNA-seq dataset assigned for the second biological replicate of the six-hour hypoxia treatment.

| Sample Information | Description |
|---|---|
| Student | Deguit, Zenas Charis C. |
| Group | Group 2 |
| Assigned Topic | Hypoxia |
| Sample Name | Hypoxia6h_R2 |
| Original Sample Name | HS_360min_02 |
| NCBI SRA Run | `SRR26073703` |
| BioProject | `PRJNA1017894` |
| Experimental Condition | Hypoxia treatment |
| Oxygen Concentration | 1% O₂ |
| Exposure Duration | 360 minutes (6 hours) |
| Biological Replicate | Replicate 2 |
| Organism | *Homo sapiens* |
| Cell Type | Human placental artery-derived endothelial cells |

---

## Selected RNA-Seq Study

### Reference

Allen, K. N., et al. (2024). Hypoxia exposure blunts angiogenic signaling and upregulates the antioxidant system in endothelial cells derived from elephant seals. *BMC Biology, 22*, 92.

- **DOI:** [10.1186/s12915-024-01892-3](https://doi.org/10.1186/s12915-024-01892-3)
- **RNA-seq Repository:** NCBI Sequence Read Archive (SRA)
- **BioProject:** `PRJNA1017894`
- **Sequencing Platform:** Illumina NovaSeq
- **Reference Genome:** Human GRCh38
- **Primary Analysis Tools:** STAR, RSEM, and EBSeq

### Biological Objective

The study examined the effects of reduced oxygen availability on gene expression in endothelial cells. In particular, the researchers investigated transcriptional changes associated with angiogenic signaling and antioxidant defense mechanisms following hypoxic exposure.

---

## Experimental Design

The primary experimental variable was oxygen availability. Cells maintained under normoxic conditions and collected at 0 minutes were used as the control group. Cells exposed to 1% oxygen for 360 minutes represented the hypoxia treatment group.

| Experimental Group | Oxygen Condition | Exposure Time | Biological Replicates |
|---|---|---:|---:|
| Control | Normoxia | 0 minutes | 3 |
| Treatment | 1% O₂ | 360 minutes | 3 |

The assigned sample, `SRR26073703`, represents the second biological replicate of the six-hour hypoxia treatment.

---

## Sample Classification

The sample can be classified according to the following experimental conditions:

```text
Experimental Study
        |
        +-- Control
        |     |
        |     +-- Normoxia
        |     +-- 0 minutes
        |     +-- n = 3
        |
        +-- Hypoxia Treatment
              |
              +-- 1% O₂
              +-- 360 minutes (6 hours)
              +-- n = 3
                    |
                    +-- Hypoxia6h_R2
                        SRR26073703
