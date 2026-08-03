```markdown
# Assembly-Quality Contamination Screening and Its Impact on Antimicrobial Resistance Predictions for Typhoid Fever Treatment

This repository accompanies a reanalysis of the Global Typhoid Genomics Consortium (GTGC) dataset, testing whether assembly-quality screening measurably changes reported antimicrobial resistance (AMR) prevalence in *Salmonella* Typhi, and whether any such change reflects a genuine difference in genotype-call accuracy rather than an artefact of exclusion.

## Structure

```
├── notebooks/
│   └── STyphi_CoLab_Final.ipynb   # Full analysis pipeline
├── data/
│   ├── gtgc_raw_input.csv         # GTGC line list (13,003 genomes, 57 countries)
│   └── styphi_amrnet_export.json  # AMRnet cross-check export
├── results/
│   ├── gtgc_vs_amr_results_summary.csv
│   ├── table1_arm_a_vs_b.csv          # Manuscript Table 1: Arm A vs Arm B prevalence
│   ├── table2_negative_control.csv    # Manuscript Table 2: placebo negative control
│   ├── table4_amrnet_concordance.csv  # Manuscript Table 3: AMRnet concordance
│   └── table5_ast_concordance.csv     # Manuscript Table 4: lab-confirmed AST validation
└── figures/
    ├── fig1_dataset_characterisation.* # Geographic and temporal distribution
    ├── fig2_arm_comparison.*           # Prevalence shift significance and negative control
    ├── fig3_amrnet_concordance.*       # Concordance with AMRnet by flag status
    └── fig4_ast_concordance.*          # Concordance with lab-confirmed phenotype
```

Each figure is provided as PDF, PNG, and TIFF.

## Pipeline summary

A contamination-risk flag was constructed from genome length (outside the 2.5th–97.5th percentile), N50 (<20,000), contig count (>200), and the consortium's own `exclude_assembly` indicator. Resistance prevalence was compared between the full dataset (Arm A, n=13,003) and the flagged-excluded subset (Arm B, n=12,166) across six drug-class outcomes using chi-square tests, odds ratios, and Benjamini-Hochberg correction. A randomly permuted negative control (seed=42) was used to distinguish genuine signal from exclusion-of-any-subset artefacts. Calls were cross-checked against AMRnet and against lab-confirmed phenotypic AST data from the GTGC consortium's Mykrobe validation resource.

Full methodological detail is in the manuscript; the notebook in `notebooks/` reproduces every reported statistic and figure.

## Data provenance

- **Primary dataset:** fetched programmatically from the GTGC consortium's public repository. File integrity was recorded via SHA-256 hash at time of fetch (prefix: `9ec9addb3ed63e62`).
- **Independent cross-check:** AMRnet, an independently curated global AMR surveillance resource.
- **Phenotypic validation:** the GTGC consortium's Mykrobe validation resource (lab-confirmed antimicrobial susceptibility testing data).
- No raw sequencing reads were generated, accessed, or deposited as part of this work — all inputs are pre-existing, publicly available consortium outputs.

## Reproducing the analysis

The notebook was run in Google Colaboratory using Python 3.12.13 with pandas, NumPy, SciPy, statsmodels, matplotlib, and seaborn. Open `notebooks/STyphi_CoLab_Final.ipynb` in Colab or a local Jupyter environment with these packages installed; input data paths assume the repository's folder structure above.

## Citation

A full citation with DOI will be added here upon publication.

## License

Code in this repository is released under the [MIT License](LICENSE). Data files are derived from publicly available consortium resources (GTGC, AMRnet, Mykrobe) — see Data provenance above for original sources and their respective usage terms.
```
