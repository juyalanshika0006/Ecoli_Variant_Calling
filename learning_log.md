# E. coli Variant Calling Project — Learning Log

## Day 1 — FASTQ Quality Control

### Dataset
- Organism: Escherichia coli
- Sample: SRR2584866
- Data type: Paired-end FASTQ
- Files:
  - SRR2584866_1.trim.sub.fastq
  - SRR2584866_2.trim.sub.fastq

### Quality Control
FastQC was performed on both paired-end FASTQ files.

### FastQC observations

Both reads showed:
- PASS: Basic Statistics
- PASS: Per base sequence quality
- PASS: Per sequence quality scores
- PASS: Per tile sequence quality
- PASS: Per base N content
- PASS: Sequence Duplication Levels
- PASS: Overrepresented Sequences
- PASS: Adapter Content

Warnings/issues:
- Read 1: Per base sequence content — FAIL
- Read 2: Per base sequence content — WARN
- Both reads: Per sequence GC content — WARN
- Both reads: Sequence Length — WARN

### Interpretation
The base quality and overall read quality passed FastQC checks.
The warnings related mainly to nucleotide composition, GC distribution,
and sequence length. These results will be considered before downstream
alignment.

### Tools Used
- Linux/WSL
- FastQC