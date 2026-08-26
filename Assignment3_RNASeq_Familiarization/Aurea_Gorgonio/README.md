#  RNA-Seq Data Familiarization and Quality Characterization

### Control_R3 — Normoxic Control Endothelial Cells

**Assignment 3 | Group 2: Hypoxia**

---

**Student:** Gorgonio Aurea
**NCBI SRA Run:** SRR26073701
**BioProject:** PRJNA1017894

---

##  Sample Overview

This README documents the import, characterization, and quality-control assessment of the third normoxic control biological replicate from a published RNA-seq study.

| Sample Information       | Description                                      |
| ------------------------ | ------------------------------------------------ |
| **Student**              | Gorgonio Aurea                                   |
| **Group**                | Group 2                                          |
| **Assigned topic**       | Hypoxia                                          |
| **Sample name**          | Control_R3                                       |
| **Original sample name** | HS_0min_03                                       |
| **Run accession**        | SRR26073701                                      |
| **BioProject**           | PRJNA1017894                                     |
| **Condition**            | Normoxic control                                 |
| **Oxygen concentration** | Normoxia                                         |
| **Exposure duration**    | 0 minutes                                        |
| **Biological replicate** | Control replicate 3                              |
| **Organism**             | *Homo sapiens*                                   |
| **Cell type**            | Human placental artery-derived endothelial cells |

---

##  Selected RNA-Seq Study

### Citation

Allen, K. N., et al. (2024). *Hypoxia exposure blunts angiogenic signaling and upregulates the antioxidant system in endothelial cells derived from elephant seals.* **BMC Biology, 22**, 92.

* **DOI:** 10.1186/s12915-024-01892-3
* **RNA-seq repository:** NCBI Sequence Read Archive
* **BioProject:** PRJNA1017894
* **Sequencing platform:** Illumina NovaSeq
* **Reference genome:** Human GRCh38
* **Authors' primary RNA-seq tools:** STAR, RSEM, and EBSeq

### Biological Question

The study investigated how hypoxia alters gene expression and cellular-response pathways in endothelial cells, particularly angiogenic signaling and antioxidant-defense mechanisms.

---

##  Experimental Design

The independent variable was oxygen availability. Normoxic endothelial cells collected at 0 minutes served as the control condition, while cells exposed to 1% oxygen for six hours served as the hypoxia treatment.

| Experimental Group | Oxygen Condition |                  Time | Replicates |
| ------------------ | ---------------- | --------------------: | ---------: |
| **Control**        | Normoxia         |             0 minutes |          3 |
| **Treatment**      | 1% O₂            | 360 minutes / 6 hours |          3 |

```mermaid
flowchart LR
    A[Endothelial cells] --> B[Normoxic control]
    B --> C[RNA extraction]
    C --> D[Paired-end RNA sequencing]
    D --> E[FASTQ quality assessment]
```

---

##  Assigned RNA-Seq Run

| Sample         | SRA Accession   | Original Sample | Condition        |
| -------------- | --------------- | --------------- | ---------------- |
| **Control_R3** | **SRR26073701** | HS_0min_03      | Normoxic control |

The selected run represents the third biological replicate of the normoxic control group.

---

##  Galaxy Procedure

The assigned SRA run was imported into an individual Galaxy history using **Faster Download and Extract Reads in FASTQ Format from NCBI SRA**.

The run produced paired-end forward and reverse read collections. **FastQC v0.12.1** was applied to both mates.

Genome alignment, gene counting, transcript quantification, and differential-expression analysis were not performed because they were outside the scope of this familiarization activity.

---

##  FASTQ File Structure

A FASTQ record contains four lines:

1. A sequence identifier beginning with `@`
2. The nucleotide sequence
3. A separator line beginning with `+`
4. ASCII characters representing Phred quality scores

Unlike FASTA, FASTQ contains base-specific quality information.

---

##  RNA-Seq Characterization

| Characteristic                 | Observation                                                                   |
| ------------------------------ | ----------------------------------------------------------------------------- |
| **Read type**                  | Paired-end                                                                    |
| **Read length**                | 151 bp                                                                        |
| **Encoding**                   | Sanger/Illumina 1.9                                                           |
| **GC content**                 | Approximately 51%                                                             |
| **General per-base quality**   | Predominantly above Q30                                                       |
| **Poor-quality reads flagged** | Zero sequences were flagged as poor quality in the examined reports           |
| **Adapter content**            | Adapter content increased near the 3′ ends                                    |
| **Overrepresented sequences**  | No overrepresented sequences detected                                         |
| **Sequence duplication**       | Duplication warnings occurred                                                 |
| **Overall assessment**         | High-quality library; trimming should be evaluated before downstream analysis |

The group comparison reports **Control_R3 (SRR26073701)** at approximately **38,401,605 sequences per mate** with approximately **51% GC content**. Its main FastQC observation was high overall quality with adapter-content and duplication warnings.

---

##  FastQC Interpretation

### Per-Base Sequence Quality

The sample showed predominantly high per-base Phred quality scores, with the overall group assessment indicating that the libraries were generally high quality.

A **Q30** score corresponds to an estimated base-call error probability of approximately **0.1%**, indicating high sequencing accuracy.

### GC Content

The sample had approximately **51% GC content**, which was within the range observed across the six samples. The group comparison showed GC values of approximately 50–52%, with no major compositional outlier.

### Adapter Content

Adapter sequences increased toward the **3′ end** of several libraries, including the assigned sample. Adapter sequences are technical sequences rather than biological RNA sequences and may interfere with downstream alignment and abundance estimation if they are retained.

### Sequence Duplication

Duplication warnings were observed in several samples. In RNA-seq, duplication does not necessarily indicate a failed library because highly abundant transcripts or technical amplification can contribute to duplicated reads.

---

##  Interpretation Questions

### 1. What biological question was the original study trying to answer?

The study investigated how hypoxia alters gene expression and cellular-response pathways in endothelial cells, particularly angiogenic signaling and antioxidant defense.

### 2. Why did the authors use RNA-seq instead of only examining the genome?

The genome shows which genes are present, whereas RNA-seq measures which genes are transcriptionally active and how RNA abundance changes under hypoxic conditions.

### 3. What is the difference between genomic DNA and RNA measured by RNA-seq?

Genomic DNA is relatively stable hereditary material, whereas RNA consists of transcribed gene products whose abundance can change according to oxygen concentration, cellular state, and regulatory signaling.

### 4. What is a biological replicate and why is it important?

A biological replicate is an independently prepared biological sample exposed to the same experimental condition. Replicates capture biological variation, increase statistical power, and reduce the possibility that one unusual sample determines the experimental conclusion.

### 5. What is the difference between single-end and paired-end sequencing?

Single-end sequencing reads one end of a cDNA fragment, whereas paired-end sequencing reads both ends. Paired-end sequencing produces R1 and R2 reads and can improve alignment and splice-junction detection.

### 6. What is a FASTQ file?

A FASTQ file contains sequence identifiers, nucleotide sequences, separator lines, and base-specific Phred quality scores.

### 7. What information does FastQC provide?

FastQC provides information about read count, read length, GC distribution, base quality, nucleotide composition, ambiguous bases, sequence duplication, overrepresented sequences, and adapter contamination.

### 8. What does a high per-base quality score indicate?

A high Phred quality score indicates a low probability of a base-calling error. For example, Q30 corresponds to an estimated error probability of approximately 0.1%.

### 9. Why can adapter contamination be a problem?

Adapters are technical rather than biological sequences. If they remain in the reads, they can cause mismatches, decrease alignment accuracy, and potentially bias abundance estimates.

### 10. Were all samples similar in quality?

Yes. The samples had the same paired-end structure and read length, similar GC content, and predominantly high base quality. No severe quality outlier was identified.

### 11. Did the assigned sample show a possible quality problem?

The assigned sample showed adapter-content and duplication warnings. These observations do not automatically indicate that the dataset should be discarded. Instead, adapter trimming and subsequent quality reassessment should be considered before downstream analysis.

### 12. What additional steps are required before comparing gene expression?

If justified, reads should be trimmed and reassessed, aligned to the human GRCh38 reference genome, assigned to annotated genes, normalized, and analyzed using a replicate-level differential-expression model with adjusted p-values.

---

##  Sample Quality Summary

**Sample:** Control_R3
**Accession:** SRR26073701
**Condition:** Normoxia
**Read structure:** Paired-end
**Read length:** 151 bp
**GC content:** ~51%
**Per-base quality:** Predominantly high / above Q30
**Adapter warning:** Present
**Duplication warning:** Present
**Overrepresented sequences:** Not detected
**Overall quality:** High quality, with trimming evaluation recommended

---

##  Conclusion

The assigned RNA-seq run, **Control_R3 (SRR26073701)**, was successfully characterized as a 151-bp paired-end RNA-seq dataset representing a normoxic endothelial-cell control. The sample showed approximately 51% GC content and predominantly high per-base sequencing quality. FastQC observations identified adapter-content and sequence-duplication warnings, but no major quality failure was evident.

Overall, the sample provides a suitable raw-data foundation for subsequent RNA-seq analysis. Before downstream expression analysis, adapter trimming should be evaluated and the reads should be reassessed for quality. Subsequent steps would include alignment to GRCh38, gene counting, normalization, and differential-expression analysis.

---

##  Required GitHub Evidence

The student folder should contain:

* [ ] Galaxy history
* [ ] FASTQ four-line preview
* [ ] FastQC Basic Statistics
* [ ] FastQC Per Base Sequence Quality
* [ ] FastQC Adapter Content or another relevant warning
* [ ] This `README.md`
* [ ] Assigned SRA accession: **SRR26073701**

> **Note:** Large FASTQ files should not be uploaded to GitHub.

---

###  Student

**Gorgonio Aurea**
**Group 2 — Hypoxia**
**Assignment 3: RNA-Seq Literature Familiarization and Data Characterization**
