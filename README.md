# Analysis notebook for the provided figure

# ChEC Data preprocessing:
The data (raw reads fastqs) was downloaded from the GEO, 
The reads were aligned using Bowtie2 with the options “‐‐end-to-end ‐‐trim-to 40 ‐‐very-sensitive”.
The genome coverage of fully aligned read pairs was calculated with GenomeCoverage by BEDTools using the parameters “-d –5 –fs 1”, 
resulting in the position of the fragment ends, which correspond to the actual MNase cutting sites. 
Number of the reads was normalized to 10^7, excluding the ribosomal locus on the XII chromosomes and CUP1/2 genes regions.
Promoters were defined only for genes with an annotated transcript. The length of each promoter was defined as 700 bps upstream to the transcription start site (TSS) or to the position where a promoter meets another transcript. The signal across each promoter was summed to calculate the overall promoter binding for each sample. The promoters of subtelomeric genes were excluded from the analyses.

# RNA Data preprocessing:
The data (gene-counts) was downloaded from the GEO,
Reads were normalized to 1e6, and for each repsective sample log2(FC) was calculated as log2(DMSO+1) - log2(IAA+1).

# External Data
### Identities of the genes for the GO pathways in figure C were extracted using gseapy python package https://gseapy.readthedocs.io/en/latest/gseapy_example.html

### Data for the alpha-factor response was obtained from - https://pubmed.ncbi.nlm.nih.gov/10657304/

### Data for the Environmental Stress Response was obtained from - https://pmc.ncbi.nlm.nih.gov/articles/PMC15070/

### TF-pwms were obtained from cis-bp and one pwm per TF was used as listed in the data/tf_cisbp_mot_map.csv file
