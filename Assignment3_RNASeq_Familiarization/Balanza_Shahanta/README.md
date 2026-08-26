# Assignment 3: RNA-Seq Literature Familiarization and Data Characterization

**Student:** Balanza, Shahanta  
**Group:** Group 2  
**Assigned Topic:** Hypoxia  
**Date:** August 18, 2026 

---

## 1. Selected RNA-Seq Paper

Allen, K. N., et al. (2024). *Hypoxia exposure blunts angiogenic signaling and upregulates the antioxidant system in endothelial cells derived from elephant seals.* **BMC Biology, 22**, 92.

**DOI:** 10.1186/s12915-024-01892-3

The study investigated how hypoxia affects gene expression and cellular-response pathways in endothelial cells, particularly pathways associated with angiogenic signaling and antioxidant defense.

---

## 2. Experimental Design

The original study examined the effects of reduced oxygen availability on endothelial cells.

| Information | Group Answer |
|---|---|
| Organism / Cell type | *Homo sapiens*; human placental artery-derived endothelial cells |
| Biological question | How does hypoxia alter gene expression and cellular-response pathways in endothelial cells? |
| Control | Normoxic endothelial cells collected at 0 minutes |
| Treatment | Endothelial cells exposed to 1% O₂ for 360 minutes (6 hours) |
| Biological replicates | Three control and three hypoxia biological replicates |
| Sequencing platform | Illumina NovaSeq |
| Sequencing type | Paired-end |
| Read length | 151 bp |
| Repository | NCBI SRA |
| BioProject | PRJNA1017894 |
| Reference genome | Human GRCh38 |
| Main software | STAR, RSEM, EBSeq |

### Experimental Flow

**Control:**  
Normoxia, 0 min, n = 3  
→ RNA extraction  
→ Paired-end RNA-seq  
→ FastQC

**Treatment:**  
1% O₂, 6 h, n = 3  
→ RNA extraction  
→ Paired-end RNA-seq  
→ FastQC

---

## 3. Assigned RNA-Seq Dataset

| Characteristic | Observation |
|---|---|
| Sample | Hypoxia6h_R2 |
| SRA accession | SRR26073703 |
| Original sample | HS_360min_02 |
| Condition | Hypoxia treatment |
| Treatment | 1% O₂ for 6 hours |
| Biological replicate | Replicate 2 |
| Sequencing type | Paired-end |
| Read length | 151 bp |
| Sequences per mate | 36,859,729 |
| GC content | Approximately 50% |

The assigned dataset represents the second biological replicate of endothelial cells exposed to 1% oxygen for six hours.

---

## 4. RNA-Seq Repository

**Repository:** NCBI Sequence Read Archive (SRA)

**BioProject:** PRJNA1017894

**Assigned Run Accession:** SRR26073703

The RNA-seq data were imported into Galaxy using the Faster Download and Extract Reads in FASTQ Format tool.

The dataset produced paired forward and reverse reads.

---

## 5. FASTQ File Structure

A FASTQ record contains four lines:

1. Sequence identifier beginning with `@`
2. Nucleotide sequence
3. Separator line beginning with `+`
4. Quality-score characters representing the quality of each nucleotide

FASTQ differs from FASTA because FASTA contains sequence identifiers and nucleotide sequences but does not contain base-specific sequencing quality scores.

Quality scores are important because they indicate the confidence of each base call and allow researchers to identify low-quality sequencing data.

---

## 6. FastQC Analysis

FastQC v0.12.1 was performed on both paired-end mates of the assigned RNA-seq dataset.

### Basic Statistics

- **Sequences per mate:** 36,859,729
- **Read length:** 151 bp
- **GC content:** Approximately 50%
- **Encoding:** Sanger / Illumina 1.9

### Per Base Sequence Quality

The per-base sequence quality was predominantly above Q30, indicating generally high sequencing quality across the reads.

A high Phred quality score indicates a low probability of an incorrect base call. A Q30 score corresponds to an estimated base-call error probability of approximately 0.1%.

### Adapter Content

Adapter content increased toward the 3′ ends of the reads. This indicates that adapter sequences may be present in some reads and should be evaluated for trimming before downstream analysis.

### Overrepresented Sequences

No overrepresented sequences were detected in the examined FastQC report.

### Sequence Duplication

Duplication warnings occurred in the dataset. In RNA-seq data, duplication does not necessarily indicate a technical problem because highly expressed transcripts can naturally produce repeated sequences. However, the duplication pattern should still be considered during quality assessment.

### Overall FastQC Assessment

The assigned RNA-seq dataset showed generally high sequencing quality. The main observations were increased adapter content near the 3′ ends and sequence duplication. Adapter trimming should be evaluated before downstream alignment and expression analysis.

---

## 7. Interpretation Questions

### 1. What biological question was the original RNA-seq study trying to answer?

The study investigated how hypoxia alters gene expression and cellular-response pathways in endothelial cells, particularly pathways involved in angiogenic signaling and antioxidant defense.

### 2. Why did the authors use RNA-seq instead of only examining the genome?

The genome shows which genes are present, whereas RNA-seq measures which genes are being transcribed and how their RNA abundance changes under different conditions.

### 3. What is the difference between genomic DNA and the RNA molecules measured by RNA-seq?

Genomic DNA is the relatively stable hereditary material containing genetic information. RNA molecules are produced from expressed genes, and their abundance can change depending on oxygen availability, cell state, and regulatory signals.

### 4. What is a biological replicate and why is it important?

A biological replicate is an independently prepared biological sample exposed to the same experimental condition. Biological replicates allow researchers to measure natural biological variation, increase statistical reliability, and reduce the possibility that an unusual sample will determine the results.

### 5. What is the difference between single-end and paired-end sequencing?

Single-end sequencing reads one end of a cDNA fragment. Paired-end sequencing reads both ends of the fragment, producing R1 and R2 reads. Paired-end sequencing provides additional information that can improve alignment and detection of transcript features such as splice junctions.

### 6. What is a FASTQ file?

A FASTQ file contains sequencing read identifiers, nucleotide sequences, separator lines, and base-specific Phred quality scores.

### 7. What information does FastQC provide?

FastQC provides information about sequencing quality, including read number, read length, GC content, per-base sequence quality, nucleotide composition, sequence duplication, overrepresented sequences, and adapter contamination.

### 8. What does a high per-base quality score indicate?

A high Phred quality score indicates a low probability of an incorrect base call. A Q30 score corresponds to an estimated base-call error probability of approximately 0.1%.

### 9. Why can adapter contamination be a problem?

Adapter sequences are technical sequences added during library preparation and are not part of the biological RNA sequence. If adapters remain in the reads, they can interfere with alignment and potentially affect downstream transcript or gene abundance estimates.

### 10. Were all RNA-seq samples in your group similar in quality?

Yes. The group samples had the same paired-end structure and 151-bp read length, with similar GC content and predominantly high per-base quality. No major quality outlier was identified.

### 11. Did any sample show a possible quality problem?

The assigned sample showed increased adapter content toward the 3′ end and sequence duplication warnings. These observations do not necessarily mean that the sample must be discarded, but adapter trimming should be evaluated before downstream analysis.

### 12. What additional steps would be needed before comparing gene expression between control and treatment samples?

If necessary, the reads should first be trimmed and reassessed for quality. The reads would then need to be aligned to the reference genome, assigned to annotated genes, normalized, and analyzed using an appropriate differential-expression method that accounts for biological replicates and multiple testing.

---

## 8. Scope of the Assignment

This activity stopped at RNA-seq data familiarization and quality characterization.

The following steps were **not performed**:

- Genome alignment
- Transcript quantification
- Gene counting
- Differential-expression analysis

These analyses are outside the scope of this assignment.

---

## 9. Screenshots

The following screenshots are included in the `screenshots` folder:

1. Galaxy history showing the imported RNA-seq dataset
2. FASTQ preview showing the four-line structure
3. FastQC Basic Statistics
4. FastQC Per Base Sequence Quality
5. FastQC Adapter Content

---

## 10. Conclusion

The assigned RNA-seq run, SRR26073703, was successfully imported into Galaxy and characterized as a 151-bp paired-end RNA-seq dataset. The sample contained 36,859,729 sequences per mate and had approximately 50% GC content with predominantly high per-base quality. FastQC identified increased adapter content toward the 3′ ends and sequence duplication warnings as the main quality observations. Overall, the dataset showed generally good sequencing quality and provides a suitable starting point for further RNA-seq analysis after appropriate quality-control and preprocessing steps.
