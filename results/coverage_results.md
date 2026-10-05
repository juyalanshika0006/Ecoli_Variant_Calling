# E. coli Coverage Analysis Results

## Dataset

**Sample:** SRR2584866

**Reference:** E. coli B strain REL606

**Reference accession:** CP000819.1

## Coverage Tool

Coverage statistics were calculated using **SAMtools** from the coordinate-sorted BAM file.

Command used:

    samtools coverage SRR2584866_sorted.bam

## Coverage Results

| Metric | Result |
|---|---:|
| Reference | CP000819.1 |
| Reference length | 4,629,812 bp |
| Reads | 351,103 |
| Covered bases | 3,460,683 |
| Coverage breadth | 93.02% |
| Mean depth | 9.74× |
| Mean base quality | 35.4 |
| Mean mapping quality | 58.2 |

## Interpretation

The sequencing reads provided an average coverage depth of approximately **9.74×** across the reference genome.

Approximately **93.02% of the reference genome** was covered by at least one sequencing read.

The mean base quality of **35.4** indicates generally high base-call quality, while the mean mapping quality of **58.2** indicates that the reads were mapped to the reference with high mapping confidence.

The coverage results indicate that the aligned dataset provides sufficient information for practicing downstream variant calling, while low-coverage regions should be considered carefully during variant interpretation.

## Files Used

The coverage analysis was performed using:

    results/SRR2584866_sorted.bam

The large BAM file is retained locally and is not uploaded to GitHub.

## Next Step

The next stage of the project is:

**Variant Calling → VCF Generation → Variant Filtering → Biological Interpretation**
