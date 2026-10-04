# E. coli Alignment Results

## Dataset

**Sample:** SRR2584866

**Reference:** E. coli B strain REL606

**Reference accession:** CP000819.1

## Alignment Tool

The sequencing reads were aligned to the E. coli reference genome using **BWA MEM**.

Command used:

    bwa mem \
    "references/GCA_000017985.1_ASM1798v1_genomic (1).fna" \
    "reads/SRR2584866_1.trim.sub.fastq" \
    "reads/SRR2584866_2.trim.sub.fastq" \
    > results/SRR2584866.sam

## SAM to BAM Conversion

The SAM alignment file was converted into BAM format using SAMtools.

    samtools view -b results/SRR2584866.sam \
    > results/SRR2584866.bam

BAM format is a compressed binary representation of SAM and is more suitable for downstream analysis.

## BAM Sorting

The BAM file was sorted by genomic coordinates.

    samtools sort results/SRR2584866.bam \
    -o results/SRR2584866_sorted.bam

Coordinate-sorted BAM files are required for many downstream genomic analysis tools.

## BAM Indexing

The sorted BAM file was indexed using SAMtools.

    samtools index results/SRR2584866_sorted.bam

This generated the corresponding `.bai` index file.

## Alignment Statistics

Alignment statistics were calculated using:

    samtools flagstat results/SRR2584866_sorted.bam

### Results

| Metric | Result |
|---|---:|
| Total reads | 351,169 |
| Mapped reads | 351,103 |
| Mapping rate | 99.98% |
| Paired reads | 350,000 |
| Properly paired reads | 346,888 |
| Properly paired rate | 99.05% |
| Singletons | 58 |
| Reads mapped to different chromosome | 0 |

## Interpretation

The sequencing reads aligned successfully to the E. coli reference genome.

The **99.98% mapping rate** indicates that almost all sequencing reads could be aligned to the reference genome.

The **99.05% properly paired rate** indicates that the majority of paired-end reads have the expected orientation and genomic distance.

These results indicate that the alignment was successful and that the resulting sorted and indexed BAM file is suitable for downstream analysis.

## Files Generated

The following alignment files were generated during the analysis:

    results/
    ├── SRR2584866.sam
    ├── SRR2584866.bam
    ├── SRR2584866_sorted.bam
    └── SRR2584866_sorted.bam.bai

The large SAM/BAM files are retained locally because they are generated analysis files and are not necessary to upload to GitHub.

## Next Step

The next stage of the analysis will be:

**Coverage Analysis → Variant Calling → VCF Generation → Variant Filtering → Biological Interpretation**
