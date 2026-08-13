# Genome Exploration II — *Prionace glauca*

## Project Overview

This project explores the basic genome structure and sequence characteristics of the blue shark (*Prionace glauca*) genome using Galaxy. The analysis was performed using a genome assembly obtained from NCBI and included basic assembly statistics, sequence-length filtering, ORF prediction, and extraction of a specific genomic region.

## Species and Genome Information

- **Species:** *Prionace glauca* (Blue shark)
- **NCBI Assembly Accession:** GCA_057534265.1
- **Assembly Level:** Contig
- **Genome Source:** NCBI
- **FASTA file:** `Prionace_glauca_GCA_057534265.1_genomic.fna`
- **Approximate file size:** 3.29 GB

## Objective

The objective of this project was to examine the basic structure of the *Prionace glauca* genome assembly using Galaxy. The analysis focused on assembly statistics, sequence-length distribution, the effect of filtering short sequences, extraction of a selected genomic region, and identification of possible open reading frames (ORFs).

## Tools and Analysis Steps

### 1. FASTA Statistics

**Tool:** FASTA Statistics

The FASTA Statistics tool was used to determine the basic characteristics of the genome assembly, including:

- Total assembly length
- Number of sequences
- Minimum sequence length
- Maximum sequence length
- Mean sequence length
- N50
- L50
- GC content

### 2. Sequence-Length Calculation

**Tool:** Compute sequence length

The sequence lengths of the genome contigs were calculated so that the sequences could be examined and sorted according to their size.

### 3. Sequence Sorting

**Tool:** Sort on dataset

The genome sequences were sorted according to sequence length to identify the longest sequences in the assembly.

### 4. Sequence-Length Filtering

**Tool:** Filter sequences by length

**Important parameter:**
- Minimum sequence length: 10,000 bp

The purpose of this step was to determine whether sequences shorter than 10 kb contributed substantially to the assembly. No sequences were removed because the shortest sequence was already 15,177 bp.

Therefore, the total assembly length, number of sequences, maximum sequence length, N50, and GC content remained unchanged after filtering.

### 5. Extracting a Specific Genomic Region

**Tool:** bedtools getfasta

A BED file was used to define the genomic region to be extracted from the FASTA genome assembly.

**Important settings:**
- BED file: selected genomic coordinates
- FASTA file: genome sequence
- Output: FASTA sequence

The selected region was then used for the ORF analysis.

### 6. ORF Prediction

**Tool:** getorf  
**Galaxy Version:** 5.0.0.1

The extracted sequence was analyzed to identify possible open reading frames (ORFs).

**Important settings:**

- Code to use: Standard
- Minimum nucleotide size of ORF to report: 300 bp
- Maximum nucleotide size of ORF to report: 1,000,000 bp
- Output: Translation of regions between STOP codons
- All START codons code for Methionine: Yes
- Circular sequence: No
- Find ORFs in the reverse complement: Yes
- Number of flanking nucleotides: 100
- Output sequence format: FASTA (m)

The analysis produced **212 ORF sequences**.

The longest ORF reported in the project results was:

- **ORF:** 0-99826_207
- **Region:** 4911–2020
- **Length:** 2,891 nucleotides

### 7. Galaxy History

The Galaxy History records the sequence of analysis steps used in this project, including the original genome dataset, statistics, filtering, sorting, sequence extraction, and ORF prediction.

The important Galaxy History steps were:

1. Original *Prionace glauca* genome FASTA
2. FASTA Statistics
3. Compute sequence length
4. Sort sequences
5. Filter sequences by length
6. FASTA Statistics after filtering
7. BED file containing the selected region
8. bedtools getfasta
9. getorf
10. FASTA statistics of the ORF output

## Results and Interpretation

The *Prionace glauca* assembly has a total length of **3,249,041,576 bp** and contains **2,253 sequences**. The maximum sequence length is **48,602,862 bp**, while the mean sequence length is approximately **1,442,095 bp**.

The assembly appears relatively contiguous rather than highly fragmented because it contains several very long sequences. The **N50 of 8,293,440 bp** and **L50 of 96** indicate that a relatively small number of long sequences account for half of the total assembly.

The 10-kb filtering step removed **zero sequences**, because the shortest sequence was already **15,177 bp**. Therefore, sequences shorter than 10 kb did not contribute to the original assembly statistics.

The genome has a **GC content of 44.65%**, representing the proportion of guanine and cytosine bases in the assembly.

The ORF analysis identified **212 possible ORFs** in the selected region. However, these ORFs should not automatically be considered real genes because an ORF can occur by chance and additional evidence is needed to confirm whether a predicted ORF represents a functional gene.
