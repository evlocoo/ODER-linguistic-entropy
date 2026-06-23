# Release Review Checklist

## Scope Boundary

- [x] Theory-side spectral-admissibility artifact is staged.
- [x] Human-data validation artifacts are not included.
- [x] Older v1.2 notebooks are identified as archived prior materials.
- [x] README states that this release is not human empirical validation.

## Notebook

- [x] Source notebook included.
- [x] Executed notebook included.
- [x] Version lock uses "Declared reference noise level".
- [x] Final verification report is all PASS.
- [x] No known stray markdown fences remain outside the Version Lock text block.

## Outputs

- [x] Verification CSVs included.
- [x] Figures included.
- [x] `validation_manifest.json` included.
- [x] Full spectral package zip included under `release-notes/` for transfer review.

## Public Repo Prep

- [x] Proposed README drafted for review.
- [x] Requirements include `scikit-learn`.
- [x] Conda environment file included.
- [x] Citation file included.
- [x] MIT license included.

## Open Reviewer Decisions

- [ ] Confirm final version label for public release.
- [ ] Confirm whether archived v1.2 notebooks should be physically moved into `archive/v1.2/` in the public repo or only linked from the archive note.
- [ ] Confirm final theory paper citation/DOI before public release.
