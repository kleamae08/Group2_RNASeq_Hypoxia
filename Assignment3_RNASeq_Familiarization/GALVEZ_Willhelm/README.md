<div align="center">

# 🧬 RNA-Seq Data Familiarization and Quality Characterization

### Hypoxia6h_R2 — Hypoxia-Treated Endothelial Cells

**Assignment 3 | Group 2: Hypoxia**

---

**Student:** Willhelm Galvez  
**NCBI SRA Run:** `SRR26073703`  
**BioProject:** `PRJNA1017894`

</div>

---

## 📌 Sample Overview

> This README documents the import, characterization, and quality-control assessment of the second six-hour hypoxia biological replicate from a published RNA-seq study.

| Sample Information | Description |
|---|---|
| **Student** | Willhelm Galvez |
| **Group** | Group 2 |
| **Assigned topic** | Hypoxia |
| **Sample name** | Hypoxia6h_R2 |
| **Original sample name** | HS_360min_02 |
| **Run accession** | `SRR26073703` |
| **BioProject** | `PRJNA1017894` |
| **Condition** | Hypoxia treatment |
| **Oxygen concentration** | 1% O₂ |
| **Exposure duration** | 360 minutes or 6 hours |
| **Biological replicate** | Hypoxia replicate 2 |
| **Organism** | *Homo sapiens* |
| **Cell type** | Human placental artery-derived endothelial cells |

---

## 📄 Selected RNA-Seq Study

**Citation**

Allen, K. N., et al. (2024). Hypoxia exposure blunts angiogenic signaling and upregulates the antioxidant system in endothelial cells derived from elephant seals. *BMC Biology, 22*, 92.

- **DOI:** [10.1186/s12915-024-01892-3](https://doi.org/10.1186/s12915-024-01892-3)
- **RNA-seq repository:** NCBI Sequence Read Archive
- **BioProject:** `PRJNA1017894`
- **Sequencing platform:** Illumina NovaSeq
- **Reference genome:** Human GRCh38
- **Authors’ primary RNA-seq tools:** STAR, RSEM, and EBSeq

### Biological Question

The study investigated how hypoxia alters gene expression and cellular-response pathways in endothelial cells. The researchers were particularly interested in angiogenic signaling and antioxidant-defense mechanisms.

---

## 🧪 Experimental Design

The independent variable was oxygen availability. Normoxic cells collected at 0 minutes served as the controls, while cells exposed to 1% oxygen for six hours served as the hypoxia treatment.

| Experimental Group | Oxygen Condition | Time | Replicates |
|---|---|---:|---:|
| **Control** | Normoxia | 0 minutes | 3 |
| **Treatment** | 1% O₂ | 360 minutes | 3 |

```mermaid
flowchart LR
    A[Endothelial cells] --> B[1% oxygen for 6 hours]
    B --> C[RNA extraction]
    C --> D[Paired-end RNA sequencing]
    D --> E[FASTQ quality assessment]
