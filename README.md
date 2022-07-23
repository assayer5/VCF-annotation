
### Overview
Parsed a VCF file to generate queries to an API, annotating the variants with API response. Unit tested functions in test_VCF_annotation_functions.

### Annotations
- NR: depth of sequence coverage at the site of variation
- NV: number of reads supporting variant
- NV/NR: percentage of reads supporting variant (vs. those supporting reference reads)
- gene: gene of variant
- type: type of variation (substitution, insertion, CNV, etc.)
- effect: effect of variation (missense, silent, intergenic, etc.)
- minor_allele_freq: minor allele frequency (if available)

### Potential Modifications/Uses
- Currently, not all variant types are annotated properly (need to cover more variant types in HGVS notation). Unknown variant types (type marked 'unknown'), are annotated by getting data with 'placeholder' HGVS notation.
- Needs more robust error/exception handling

Further use of data...
- Annotated samples could be aggregated to characterize the variants present in a population of interest
- Aggregated data could be used to train a machine learning algorithm to predict disease type or other population of interest

### Language
Python

### Packages Used
pandas, requests, json, time


### Resources
[VEP endpoints](https://rest.ensembl.org/#VEP)

[Ensembl REST API User Guide](https://github.com/Ensembl/ensembl-rest/wiki)

[HGVS notation resource](https://varnomen.hgvs.org/)
