# E. coli Variant Filtering Results

## Dataset

**Sample:** SRR2584866

**Reference:** E. coli B strain REL606

**Reference accession:** CP000819.1

## Variant Calling

Candidate variants were identified from the coordinate-sorted BAM file using BCFtools.

The initial VCF contained:

**1,025 candidate variants**

## Filtering Criteria

Variants were filtered using BCFtools based on:

- **QUAL ≥ 20**
- **DP ≥ 10**

Command used:

    bcftools filter -i 'QUAL>=20 && DP>=10' SRR2584866.vcf -o SRR2584866_filtered.vcf

Where:

- **QUAL** represents the confidence score assigned to the variant call.
- **DP** represents the read depth at the variant position.

## Filtering Results

| Metric | Count |
|---|---:|
| Initial candidate variants | 1,025 |
| Filtered variants retained | 421 |
| Variants removed | 604 |
| Percentage retained | 41.1% |

## Interpretation

The initial variant calling step identified **1,025 candidate variants**.

After applying the quality filters of **QUAL ≥ 20** and **DP ≥ 10**, **421 variants** were retained.

A total of **604 variants** were removed because they did not meet one or both quality criteria.

The filtering step therefore reduced the number of candidate variants while retaining variants supported by a minimum level of sequencing depth and variant quality.

These 421 filtered variants will be used for downstream biological interpretation.

## Files

The following VCF files were generated:

    results/
    ├── SRR2584866.vcf
    └── SRR2584866_filtered.vcf

The filtered VCF contains the higher-confidence candidate variants used for downstream analysis.

## Next Step

The next stage of the project is:

**Variant Annotation → Biological Interpretation**
