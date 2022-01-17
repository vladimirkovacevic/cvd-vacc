# Comparison of current vaccine targets to SARS-CoV-2 circulating in 2022


## Analysis
Pfizer–BioNTech and Moderna SARS-CoV-2 vaccines contain uRNA that codes identical full-length SARS-CoV-2 spike glycoprotein (1257 aminoacids). Astrazeneca vaccine spike protein differs two aminoacids from it. The analysis shows comparison of spike protein from Pfizer vaccine with SARS-CoV-2 currently circulating in the population.

## How to run
1. Create blastp index
```makeblastdb -in data/proteins.faa -dbtype prot -parse_seqids -input_type fasta```
2. Run blastp ```blastp -db data/proteins.faa -query data/pfizer_s_protein.faa -out results.csv -outfmt 7 -max_target_seqs 99999999```
   (blastp outputs only first 500 hits by default)
3. Process ```results.csv``` in the ```covid_vaccine.ipynb```

## Results
Comparison of 53165 SARS-CoV-2 spike protein sequences submitted to [NCBI](https://www.ncbi.nlm.nih.gov/datasets/coronavirus/proteins/) in first two weeks of 2022 to Pfizer–BioNTech vaccine's spike protein. 

The median of similarity is 97.14, mean 97.59, std 1.55.
|       |     % identity |     mismatching amino acids |
|-------|---------------:|---------------:|
| count | 53.165.000.000 | 53.165.000.000 |
|  mean |     97.593.773 |     25.033.876 |
|   std |      1.552.217 |     16.804.976 |
|   min |     82.980.000 |      2.000.000 |
|   25% |     96.670.000 |     11.000.000 |
|   50% |     97.140.000 |     29.000.000 |
|   75% |     98.970.000 |     33.000.000 |
|   max |     99.840.000 |    212.000.000 |

![](https://github.com/vladimirkovacevic/cvd-vacc/blob/main/results/results_latest_53165.csv.png)



