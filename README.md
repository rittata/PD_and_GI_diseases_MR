This repository contains code used for my first year master's project at ITMO University.  

I used a two sample [Mendelian randomisation](https://en.wikipedia.org/wiki/Mendelian_randomization) (MR) method to obtain previously unpublished causal relationships between several gastrointestinal diseases (chronic and acute pancreatitis, diverticular disease, peptic ulcer disease) and Parkinson's disease (PD risk, age at onset, and PD-related phenotypes: cognitive impairment, several standardised motor and cognitive scales). In addition, MR analyses were performed for vitamin B12 levels and GI diseases to validate the results obtained in the first semester (see [report](https://drive.google.com/file/d/1GyNfPNlcYvsMLIwNGCRs4NdajW5yY82Y/view?usp=drive_link)). Details of the data sets are given in the table:

| Trait |	Abbreviation used in code |	GWAS study |	Data source |	Prevalence source* |	Trait type |	N cases |	N controls |	Sample size |
| --- |	--- |	--- |	--- |	--- |	--- |	--- |	--- |	--- |
| ***Exposure data*** |	 |	 |	 |	 |	 |	 |	 |	 |
| Alcoholic chronic pancreatitis |	Panc_Alc_Chr |	[Rosendahl et al. 2017](https://pubmed.ncbi.nlm.nih.gov/28754779/) |	Supplementary file 2 in the article; [modified dataset used in the analysis](https://drive.google.com/file/d/1ruw0SBYPfvU2nDBEnRl44Z1w5tmboRye/view?usp=drive_link)  |	[Yadav et al. 2011](https://pubmed.ncbi.nlm.nih.gov/28754779/) |	Binomial |	1959 |	6040 |	7999 |
| Non-alcoholic chronic pancreatitis |	Panc_nonAlc_Chr |	[Schmidt et al. 2022](https://pubmed.ncbi.nlm.nih.gov/35331647/) |	Article and [GWAS Catalog](https://www.ebi.ac.uk/gwas/studies/GCST90104595) info; [modified dataset used in the analysis](https://drive.google.com/file/d/10E61wQ0bROdaDtyLXcmC197o2tECQ8LK/view?usp=drive_link)  |	[Yadav et al. 2011](https://pubmed.ncbi.nlm.nih.gov/28754779/) |	Binomial |	584 |	6040 |	6624 |
| Acute pancreatitis |	Panc_Ac |	[Bourgault et al. 2023](https://pubmed.ncbi.nlm.nih.gov/36736436/) |	[Full summary statistics](http://ftp.ebi.ac.uk/pub/databases/gwas/summary_statistics/GCST90255001-GCST90256000/GCST90255375/) from GWAS Catalog |	[Li et al., 2021](https://pubmed.ncbi.nlm.nih.gov/34433418/) |	Binomial |	10630 |	844679 |	855309 |
| Diverticular disease |	DivD |	[Wu et al. 2023](https://pubmed.ncbi.nlm.nih.gov/37492107/) |	[Full summary statistics](https://cnsgenomics.com/content/data) from Progect in CTG |	[Tursi et al., 2020](https://pubmed.ncbi.nlm.nih.gov/32218442/) |	Binomial |	78399 |	645973 |	724372 |
| Peptic ulcer disease |	PUD |	[Wu et al. 2021](https://pubmed.ncbi.nlm.nih.gov/33608531/) |	[Full summary statistics from Progect in CTG](https://cnsgenomics.com/content/data) |	[Sung et al., 2009](https://pubmed.ncbi.nlm.nih.gov/19220208/) |	Binomial |	16666 |	439661 |	456327 |
| ***Outcome data*** |	 |	 |	 |	 |	 |	 |	 |	 |
| Parkinson's disease (23andMe participants excluded) |	PD_yesUKBB |	[Nalls et al. 2019](https://pubmed.ncbi.nlm.nih.gov/31701892/) | - |	[Pringsheim et al., 2014](https://pubmed.ncbi.nlm.nih.gov/24976103/) |	Binomial |	33674 |	449056 |	482730 |
| Parkinson's disease (UKB and 23andMe participants excluded) |	PD_noUKBB |	[Nalls et al. 2019](https://pubmed.ncbi.nlm.nih.gov/31701892/) |	[Full summary statistics](https://www.pdgenetics.org/resources) from IPDGC  |	[Pringsheim et al., 2014](https://pubmed.ncbi.nlm.nih.gov/24976103/) |	Binomial |	15056 |	12637 |	27693 |
| Cognitive impairment (baseline and survival analysis) |	CI_base, CI_surv |	[Iwaki et al. 2019](https://pubmed.ncbi.nlm.nih.gov/31505070/) |	[Full summary statistics and reference](https://pdgenetics.shinyapps.io/pdprogmetagwasbrowser/) from IPDGC PD Progression Meta-GWAS Browser |	[Pais et al., 2020](https://pubmed.ncbi.nlm.nih.gov/33121002/) |	Binomial |	- |	- |	1710 |
| Part III of the Unified Parkinson's Disease Rating Scale scores |	UPDRS3 |	[Iwaki et al. 2019](https://pubmed.ncbi.nlm.nih.gov/31505070/) |	[Full summary statistics and reference](https://pdgenetics.shinyapps.io/pdprogmetagwasbrowser/) from IPDGC PD Progression Meta-GWAS Browser |	- |	Continuous |	- |	- |	1398 |
| Mini-Mental State Examination scores |	MMSE |	[Iwaki et al. 2019](https://pubmed.ncbi.nlm.nih.gov/31505070/) |	[Full summary statistics and reference](https://pdgenetics.shinyapps.io/pdprogmetagwasbrowser/) from IPDGC PD Progression Meta-GWAS Browser |	- |	Continuous |	- |	- |	1329 |
| Hoehn and Yahr scale |	HY |	[Iwaki et al. 2019](https://pubmed.ncbi.nlm.nih.gov/31505070/) |	[Full summary statistics and reference](https://pdgenetics.shinyapps.io/pdprogmetagwasbrowser/) from IPDGC PD Progression Meta-GWAS Browser |	- |	Continuous |	- |	- |	1005 |
| Parkinson's disease age at onset |	PD_AAO |	[Blauwendraat et al. 2019](https://pubmed.ncbi.nlm.nih.gov/30957308/) |	[Full summary statistics](https://www.pdgenetics.org/resources) from IPDGC |	- |	Continuous |	- |	- |	17996 |
| B12 serum levels |	B12 |	[Dennis et al. 2021](https://pubmed.ncbi.nlm.nih.gov/33441150/) |	[Full summary statistics](http://ftp.ebi.ac.uk/pub/databases/gwas/summary_statistics/GCST90012001-GCST90013000/GCST90012772/) from GWAS Catalog |	- |	Continuous |	- |	- |	19415 |

\* Disease prevalence was used to calculate R-squared for binomial traits.

TwoSampleMR v0.6.4 and MR-PRESSO v1.0 R packages were used for the analyses.

Our results show that there is limited evidence of causality between peptic ulcer disease or diverticular disease and individual phenotypes associated with PD progression. Overall, there is no strong evidence of a causal relationship between pancreatitis, diverticular disease, peptic ulcer disease and PD or B12 levels. See the [full course project report](https://drive.google.com/file/d/11UpMdRw_T-43OaF3dYru_3YR9wXVstFU/view?usp=drive_link) for more details.
