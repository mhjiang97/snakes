# SNAKES 🐍

Catalog of Snakemake workflows for sequencing analysis. Each repository is a standalone pipeline.

Workflows share the same layout: rules in `workflow/`, conda environments in `workflow/envs/`, and a sample table via [PEP](https://pep.databio.org/). Copy the dotted templates (`config/.config.yaml` and the profile config) before the first run. Install notes are in the repositories that ship a README.

## WGS

| Pipeline | Reads | What it does |
| --- | --- | --- |
| [smk_wgs](https://github.com/mhjiang97/smk_wgs) | Illumina | QC, alignment (BWA-MEM or BWA-MEM2), GATK preprocessing, somatic SNVs and indels (Mutect2), and structural variants |
| [smk_sv_ngs](https://github.com/mhjiang97/smk_sv_ngs) | Illumina | Structural variants only (Manta, GRIDSS, SvABA, TIDDIT, Wham), then merge, filter, and annotate |
| [smk_wgs_ont](https://github.com/mhjiang97/smk_wgs_ont) | ONT, tumor-only | Long-read structural variants (cuteSV, Sniffles, SVIM, and others), merged and annotated. Early stage |
| [smk_sv](https://github.com/jasonwong-lab/smk_sv) | ONT, tumor-only | Same long-read structural-variant workflow, in the [jasonwong-lab](https://github.com/jasonwong-lab) org. Early stage |

Use `smk_wgs` for a short-read genome run that includes small variants. Use `smk_sv_ngs` when the question is structural variants from Illumina WGS. Use `smk_wgs_ont` or `smk_sv` for tumor-only Oxford Nanopore structural variants.

## WES

| Pipeline | Reads | What it does |
| --- | --- | --- |
| [smk_wes](https://github.com/mhjiang97/smk_wes) | Illumina | Alignment (BWA-MEM2), duplicate marking, base quality recalibration, and pileup |

## RNA-seq

| Pipeline | Reads | What it does |
| --- | --- | --- |
| [smk_rnaseq](https://github.com/mhjiang97/smk_rnaseq) | Illumina | STAR alignment, Salmon and featureCounts quantification, small variants, Arriba fusions, and RNA editing |

## ATAC-seq

| Pipeline | Reads | What it does |
| --- | --- | --- |
| [smk_atacseq](https://github.com/mhjiang97/smk_atacseq) | Illumina | Bowtie2 alignment, MACS3 and Genrich peaks, signal tracks, TSS enrichment, FRiP, and ATAQV |

## ChIP-seq

| Pipeline | Reads | What it does |
| --- | --- | --- |
| [smk_chipseq](https://github.com/mhjiang97/smk_chipseq) | Illumina | Bowtie2 alignment, MACS3 peaks, fingerprint plots, and strand cross-correlation (phantompeakqualtools) |

## CUT&RUN

| Pipeline | Reads | What it does |
| --- | --- | --- |
| [smk_cutrun](https://github.com/mhjiang97/smk_cutrun) | Illumina | Bowtie2 alignment, duplicate marking, and SEACR peak calling |

## Other

| Pipeline | What it does |
| --- | --- |
| [smk_downloader](https://github.com/mhjiang97/smk_downloader) | Download SRA FASTQs and slice GDC BAMs, then run FastQC and MultiQC |
