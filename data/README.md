# Sequencing test data

## Files

| Path | Contents |
| --- | --- |
| [insilico/reads/](insilico/reads/) | Simulated, downsampled paired-end reads |
| [real/](real/) | In-house paired-end reads |
| [insilico/references/](insilico/references/) | Reference FASTA files used to generate the reads |
| [test_samplesheet.csv](../samplesheets/test_samplesheet.csv) | Sample names and read URLs |

## Insilico read generation

Reads were generated with [InSilicoSeq v2.0.0](https://insilicoseq.readthedocs.io/en/latest/) using the [reference FASTA files](insilico/references/) and the following parameters:

- `--model novaseq`
- `--abundance uniform` for mixed-pathogen read sets

Each resulting sample contained 500,000 paired-end read pairs (2 x 151 bp) that were then downsampled.

## Real data

Data generated in-house.

- `NTC1_QC00094077_90586-1855-A1_S158_masked`: Generated on NextSeq 2000

## Downsampling

The resulting reads were randomly downsampled to a target depth of **100×** using [seqtk v1.5-r133](https://github.com/lh3/seqtk) with **seed 11**. The target number of sequenced bases was calculated as `genome length × 100`.
