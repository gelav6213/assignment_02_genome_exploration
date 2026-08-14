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

## Tools and Main Steps

1. **FASTA Statistics** — calculated assembly statistics including total length, number of sequences, N50, L50, and GC content.
2. **Compute Sequence Length** — determined the length of individual sequences.
3. **Sort** — ranked sequences according to their lengths.
4. **Filter Sequences by Length** — applied a ≥10 kb sequence-length filter.
5. **FASTA Statistics** — calculated statistics for the filtered assembly.
6. **getorf** — identified potential open reading frames (ORFs).

## Results and Interpretation

The *Prionace glauca* assembly has a total length of **3,249,041,576 bp** and contains **2,253 sequences**. The maximum sequence length is **48,602,862 bp**, while the mean sequence length is approximately **1,442,095 bp**.

The assembly appears relatively contiguous rather than highly fragmented because it contains several very long sequences. The **N50 of 8,293,440 bp** and **L50 of 96** indicate that a relatively small number of long sequences account for half of the total assembly.

The 10-kb filtering step removed **zero sequences**, because the shortest sequence was already **15,177 bp**. Therefore, sequences shorter than 10 kb did not contribute to the original assembly statistics.

The genome has a **GC content of 44.65%**, representing the proportion of guanine and cytosine bases in the assembly.

The ORF analysis identified **212 possible ORFs** in the selected region. However, these ORFs should not automatically be considered real genes because an ORF can occur by chance and additional evidence is needed to confirm whether a predicted ORF represents a functional gene.
