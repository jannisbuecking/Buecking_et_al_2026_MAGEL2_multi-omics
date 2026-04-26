# Buecking et al. 2026 MAGEL2 Multi-omics

This repository contains the custom analysis code and associated analysis objects for:

**Multi-omics profiling reveals convergent MAGEL2-driven defects in human corticogenesis across Prader-Willi and Schaaf-Yang syndromes.**

Authors: Jannis Buecking, Baran Enes Gueler, Michael Eibl, Azmal Syed Ali, Tobias Walczuch, Tobias Beschauner, Susanne Theiss, Melanie Spanjaard, Katrin Hinderhofer, Freya Herrmann-Sim, Celine E. de Esch, Derek J.C. Tai, Michael E. Talkowski, Jeroen Krijgsveld, Christian P. Schaaf, and Magdalena Laugsch.

Lead contact: Magdalena Laugsch (magdalena.laugsch@uni-heidelberg.de)

MAMOTH Web Portal: https://jannisbuecking-mamoth.share.connect.posit.cloud/

MAMOTH source-code repository: https://github.com/jannisbuecking/MAMOTH

## Repository status

This repository is intended to remain private until publication. It will be made publicly available as of the date of publication.

The files are intentionally kept in a flat layout because the R Markdown notebooks use local relative paths. This preserves the runnable state of the curated analysis folder.

## Data and code availability

RNA-seq and mass-spectrometry data have been deposited at GEO and will be publicly available as of the date of publication. Accession numbers will be listed in the key resources table of the associated manuscript.

All custom code used for the multi-omics analysis is included in this repository. Any additional information required to re-analyze the data reported in the paper is available from the lead contact upon request.

The associated MAMOTH Shiny web-app source code and packaged app data are maintained separately at https://github.com/jannisbuecking/MAMOTH.

## Analysis notebooks

Run notebooks from the repository root so relative file paths resolve correctly.

| Order | Script | Purpose |
| --- | --- | --- |
| 1 | `FINAL_MAGEL2_RNAseq.Rmd` | RNA-seq preprocessing, differential expression, enrichment, and RNA-seq output objects. |
| 2 | `FINAL_proteomics_preprocessing.Rmd` | Proteomics preprocessing, normalization, imputation, and differential protein analysis. |
| 3 | `FINAL_ubiquitinomics_preprocessing.Rmd` | Ubiquitinomics preprocessing, normalization, imputation, and differential ubiquitination analysis. |
| 4 | `FINAL_PCA_Plots.Rmd` | PCA visualization across RNA-seq, proteome, and ubiquitome layers. |
| 5 | `FINAL_MAGEL2_interactome.Rmd` | MAGEL2 interactome curation and network analysis. |
| 6 | `FINAL_ubiprot.Rmd` | Integrated ubiquitome-proteome ratio analyses. |
| 7 | `FINAL_transcriptomics_vs_proteomics.Rmd` | Transcriptome-proteome integration, discordance analyses, RBP/miRNA motif enrichment, and supplementary exports. |
| 8 | `FINAL_BG_MAGEL2_multiOmics_plotting.Rmd` | Background-overlap multi-omics plotting, enrichment summaries, UpSet analyses, and supplementary exports. |
| 9 | `FINAL_MOFA_Jannis.Rmd` | Multi-Omics Factor Analysis (MOFA) analyses and visualization. |

## Included files

The repository includes processed R objects, spreadsheet inputs/outputs, FASTA files, and reference resources required by the notebooks. A file-level manifest with sizes, categories, and SHA-256 checksums is available at `docs/data_manifest.tsv`.

## External resources

Some notebooks access external databases or services at runtime, including Ensembl/`biomaRt`, `AnnotationHub`, `STRINGdb`, `gprofiler2`, and `msigdbr`. Results from these services can depend on database version and access date.

## Software environment

The notebooks were developed in R/R Markdown and use Bioconductor and CRAN packages including, among others, `DESeq2`, `SummarizedExperiment`, `limma`, `clusterProfiler`, `org.Hs.eg.db`, `AnnotationHub`, `biomaRt`, `STRINGdb`, `MOFA2`, `openxlsx`, `readxl`, `tidyverse`, `ComplexUpset`, `pheatmap`, and `ggplot2`.

Environment records are included:

- `renv.lock`: package lockfile generated from the local R analysis environment.
- `session_info/sessionInfo.txt`: plain-text R session information.
- `session_info/detected_package_versions.tsv`: package versions detected from notebook `library()` and `require()` calls.

See `docs/reproducibility_checklist.md` for restore and update instructions.

## Licenses

Code and scripts are licensed under the MIT License. See `LICENSE`.

Data, processed analysis objects, and result tables are intended to be shared under the Creative Commons Attribution 4.0 International License (CC BY 4.0), pending final PI/lab confirmation. See `LICENSE-DATA.md`.
