# cvd-vacc
Comparison of COVID-19 vaccines to virus circulating in the population
Coronavirus S proteins (spike glycoprotein) downloaded from https://www.ncbi.nlm.nih.gov/datasets/coronavirus/proteins/.

## Analysis
Pfizer–BioNTech and Moderna COVID-19 vaccines contain uRNA that codes identical full-length SARS-CoV-2 spike glycoprotein (1257 aminoacids). Astrazeneca vaccine spike protein differs two aminoacids from it. The analysis shows comparison of spike protein from Pfizer vaccine with SARS-CoV-2 currently circulating in the population.
. 
## How to run
1. Create blastp index```makeblastdb -in data/proteins.faa -dbtype prot -parse_seqids -input_type fasta```
2. Run blastp ```blastp -db data/proteins.faa -query data/pfizer_s_protein.faa -out results.csv -outfmt 7 -max_target_seqs 99999999```
   (blastp outputs only first 500 hits by default)
3. Process ```results.csv``` in the ```covid_vaccine.ipynb```

## Results
Comparison of 53165 sequences submitted to NCBI in 2022 until Jan 16th are processed. 
The median of similarity is 97.14, mean 9759, std 1.55.
