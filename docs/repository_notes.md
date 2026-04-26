# Repository Notes

## Layout decision

The analysis files are kept in the repository root because the original R Markdown notebooks use root-relative local filenames. Keeping the flat layout avoids changing scientific analysis code during repository preparation.

## Large files

No file in the current repository exceeds GitHub's 100 MB single-file limit. The largest file is `Table_HS_RBP.txt` at approximately 80 MB.

Git LFS is not currently installed on the local machine used to prepare this repository. If the repository grows or reviewers request additional raw objects, install Git LFS before adding files larger than roughly 50-100 MB.

## Publication release checklist

- Confirm GEO accession numbers and add them to `README.md`.
- Confirm final manuscript title and author order.
- Confirm code/data licensing with the PI/lab before making the repository public.
- Confirm that the linked MAMOTH web-app repository at https://github.com/jannisbuecking/MAMOTH is public when this repository is released.
- Re-run `renv::snapshot()` and `sessionInfo()` from the final analysis environment if the analysis machine differs from the current local environment.
- Add a tagged release corresponding to the accepted manuscript.
- Consider archiving the release with Zenodo to mint a DOI.
