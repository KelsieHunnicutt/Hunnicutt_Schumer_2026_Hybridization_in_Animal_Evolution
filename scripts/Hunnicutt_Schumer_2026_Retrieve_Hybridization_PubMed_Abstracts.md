# this script will guide you through the process of retrieving hybridization-related abstracts from PubMed

## you will need Esearch Utility from NCBI installed for this script; find it here: [https://eutils.ncbi.nlm.nih.gov/entrez/eutils/](https://eutils.ncbi.nlm.nih.gov/entrez/eutils/

## create and move to the data directory for this project
```
mkdir -p Hybridization_in_animal_evolution_review
mkdir -p Hybridization_in_animal_evolution_review/data

cd Hybridization_in_animal_evolution_review/data
```

## retrieve pubmed IDs corresponding to search query

```
# below is the search query from the manuscript; your results will very depending on the date the query is run; in the manuscript, the finalized query was run on 2Feb26

# (("Genetic Introgression"[MeSH Terms] OR "Hybrid Vigor"[MeSH Terms] OR "hybridization, genetic"[MeSH Terms] OR "Reproductive Isolation"[MeSH Terms]) AND "Animals"[MeSH Terms])'

# to actually intiate the search, run:
~/packages/edirect/esearch -db pubmed -query '(("Genetic Introgression"[MeSH Terms] OR "Hybrid Vigor"[MeSH Terms] OR "hybridization, genetic"[MeSH Terms] OR "Reproductive Isolation"[MeSH Terms]) AND "Animals"[MeSH Terms])' | ~/packages/edirect/efetch -format uid > hybridization_MESH_terms_pubmed_search_2Feb26.txt

# as of 2Feb26, this search returns 12282 hits
# from here, move to the Rmd script for abstract retrieval and data processing
```
