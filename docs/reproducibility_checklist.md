# Reproducibility Checklist

This repository includes the analysis notebooks, processed analysis objects, and environment metadata needed to re-run the custom multi-omics analyses.

## Environment records

- `renv.lock`: package lockfile generated from the local R analysis environment.
- `session_info/sessionInfo.txt`: plain-text R `sessionInfo()` output.
- `session_info/detected_package_versions.tsv`: versions of packages detected from `library()` and `require()` calls in the `FINAL*.Rmd` notebooks.

The lockfile was generated with R 4.5.1 and Bioconductor 3.21. During lockfile generation, repository metadata could not be queried from CRAN/Bioconductor in the sandboxed environment, so `renv::snapshot(..., force = TRUE)` was used to record the installed local package state.

## How to restore the R environment

From the repository root:

```r
install.packages("renv")
renv::restore()
```

Some packages and external resources are from Bioconductor and may require matching the R/Bioconductor version recorded in `renv.lock`.

## How to update the environment record

After running analyses in the final analysis environment:

```r
renv::snapshot(prompt = FALSE, force = TRUE)
sink("session_info/sessionInfo.txt")
sessionInfo()
sink()
```

Commit the updated `renv.lock` and `session_info/sessionInfo.txt`.

## External resources

Some notebooks query external services or databases at runtime:

- Ensembl via `biomaRt`
- `AnnotationHub`
- `STRINGdb`
- `gprofiler2`
- `msigdbr`

Results from these resources can depend on database version and access date. For publication release, record GEO accessions and any fixed external resource versions in `README.md`.

