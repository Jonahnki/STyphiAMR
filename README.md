# Assembly-Quality Contamination Screening and Its Impact on Antimicrobial Resistance Predictions for Typhoid Fever Treatment

Analysis code and data supporting the manuscript submitted to *Medical Microbiology and Immunology*.

## Structure

- `notebooks/` — Google Colab analysis notebook (STyphi_CoLab_Final.ipynb), containing the full pipeline: contamination-risk flag construction, comparative analysis (Arm A vs Arm B), negative control, AMRnet cross-check, and Mykrobe AST validation.
- `data/` — Input data. `gtgc_raw_input.csv` is the fetched GTGC line list (13,003 genomes); `styphi_amrnet_export.json` is the AMRnet cross-check export.
- `results/` — Derived summary tables corresponding to manuscript Tables 1–4 and the underlying results summary.
- `figures/` — Manuscript Figures 1–4, each provided as PDF, PNG, and TIFF.

## Data provenance

Primary dataset: Global Typhoid Genomics Consortium (GTGC) public repository.
Cross-validation: AMRnet (independently curated AMR surveillance resource) and the GTGC consortium's Mykrobe validation resource.
No raw sequencing reads were generated, accessed, or deposited as part of this work.

## Citation

If you use this code or data, please cite the manuscript (citation to be added on publication).
