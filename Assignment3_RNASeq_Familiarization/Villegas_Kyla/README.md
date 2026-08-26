# RNA-Seq Literature Familiarization and Data Characterization

## Student Information

**Name:** Kyla Rose D. Villegas  
**Group:** Group 2 – Hypoxia  
**Assigned Sample:** Control_R2  
**SRA Accession:** SRR26073712  
**Original Sample:** HS_0min_02  
**Condition:** Normoxic control (0 min)  
**Biological Replicate:** Control Replicate 2  

## Selected RNA-Seq Study

**Paper:** Allen, K. N., et al. (2024). *Hypoxia exposure blunts angiogenic signaling and upregulates the antioxidant system in endothelial cells derived from elephant seals.* BMC Biology, 22, 92.  
**BioProject:** PRJNA1017894  

The study investigated how hypoxia affects gene expression and cellular-response pathways in endothelial cells, particularly angiogenic signaling and antioxidant defense.

## Assigned RNA-Seq Sample

My assigned RNA-seq dataset was **Control_R2 (SRR26073712)**, corresponding to the original sample **HS_0min_02**.

This sample represents the **second biological replicate of the normoxic control condition collected at 0 minutes**.

The dataset consisted of **paired-end RNA-seq reads**, producing an **R1 forward-read file** and an **R2 reverse-read file**.

## Galaxy Procedure

The assigned SRA accession **SRR26073712** was imported into Galaxy using:

`Faster Download and Extract Reads in FASTQ Format from NCBI SRA`

The tool generated a paired collection containing the forward and reverse FASTQ reads.

The reads were then analyzed using:

`FastQC v0.12.1`

FastQC was performed on both R1 and R2 reads to evaluate sequencing quality.

## FASTQ File Structure

A FASTQ record contains four lines:

1. Read identifier beginning with `@`
2. Nucleotide sequence
3. Separator line beginning with `+`
4. ASCII characters representing Phred quality scores

FASTQ differs from FASTA because FASTQ contains base-specific sequencing quality information.

## FastQC Results

- **Read type:** Paired-end
- **Read length:** 151 bp
- **Sequences per mate:** 35,903,149
- **GC content:** Approximately 51%
- **Encoding:** Sanger / Illumina 1.9
- **Per-base sequence quality:** Predominantly above Q30
- **Poor-quality sequences:** No major poor-quality sequence problem detected
- **Adapter content:** Adapter-content warning detected toward the 3' end
- **Sequence duplication:** Duplication warning observed
- **Overall assessment:** Generally high-quality RNA-seq data

## FastQC Interpretation

The FastQC results showed that **SRR26073712 was generally a high-quality RNA-seq dataset**.

Most bases had Phred quality scores above **Q30**, indicating a low probability of incorrect base calling. A Q30 score corresponds to an estimated sequencing error probability of approximately **0.1%**.

The GC content was approximately **51%**, which was consistent with the other samples in the experiment.

The main quality-control concerns were **adapter contamination and sequence duplication**.

Adapter sequences are technical sequences introduced during library preparation. If they remain in the reads, they may reduce alignment accuracy. Therefore, adapter trimming should be evaluated before downstream analysis.

Sequence duplication does not automatically indicate poor RNA-seq quality because highly expressed transcripts may naturally produce repeated reads. However, excessive duplication may also result from PCR amplification.

## Biological Interpretation

Control_R2 serves as a **normoxic control replicate** for comparison with endothelial cells exposed to hypoxia.

Biological replicates are important because they represent independently prepared biological samples under the same experimental condition. They allow biological variability to be measured and improve the statistical reliability of differential gene-expression analysis.

RNA-seq was used because it measures **RNA transcript abundance**, allowing researchers to determine which genes change their transcriptional activity under hypoxic conditions.

## Recommended Downstream Analysis

Before differential gene-expression analysis, the following steps should be performed:

1. Evaluate and perform adapter trimming if necessary
2. Run FastQC again on trimmed reads
3. Align reads to the appropriate reference genome
4. Assign aligned reads to annotated genes
5. Generate gene-count data
6. Normalize gene-expression counts
7. Compare control and hypoxia biological replicates using differential-expression analysis

## Conclusion

The assigned **Control_R2 (SRR26073712)** sample contained **151-bp paired-end RNA-seq reads** with approximately **51% GC content** and predominantly high per-base sequencing quality.

FastQC showed that the library was generally suitable for downstream RNA-seq analysis. The principal warnings were **adapter content and sequence duplication**.

Overall, SRR26073712 provides a suitable **normoxic biological replicate** for comparison with hypoxia-treated samples.
