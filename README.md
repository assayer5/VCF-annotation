
### Overview
Parsed text of a VCF file to generate queries to a database API, annotated the file with data from API response, unit tested functions.

### Some Details
In genetics, A Variant Call Format (VCF) file is the text output comparing a sequenced sample (the 'genome of interest') to a reference genome. VCF files tabulate the strings of nucleotides in the sample that don't match the reference genome. These variations in the genome sequence can sometimes be linked to a particular trait or disease. 

To extract further information from a VCF file, I parse the text of the file and access an online database via API to request information on each variant. I used the data pulled from the database to annotate the sequence variants with additional information. 


Although these notebooks can easily be converted to Python files, the notebook format conveniently shows the code output:
>*VCF_annotation.ipynb* - the main file used to parse the VCF file and query the database
>
>*VCF_annotation_functions.ipynb* - functions used to parse and format the data, separated from the main file for neatness
>
>*test_VCF_annotation_functions.ipynb* - unit testing functions

Annotations used:
- NR: depth of sequence coverage at the site of variation
- NV: number of reads supporting variant
- NV/NR: percentage of reads supporting variant (vs. those supporting reference reads)
- gene: gene of variant
- type: type of variation (substitution, insertion, CNV, etc.)
- effect: effect of variation (missense, silent, intergenic, etc.)
- minor_allele_freq: minor allele frequency (if available)

 Potential Modifications/Uses:
- Currently, not all variant types are annotated properly (need to cover more variant types in HGVS notation). Unknown variant types (type marked 'unknown'), are annotated by getting data with 'placeholder' HGVS notation.

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
