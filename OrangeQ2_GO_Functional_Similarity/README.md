### Orange CQ#2

**Query:**  What genes express proteins that are functionally similar to the 11 Fanconi Anemia core complex genes (set FA-core), based on GO annotations?

**Goal:** This query aims to expand the FA-core gene set based on GO functional similarity, in service of Task 1 in the St. Jude Life Cohort Demonstrator described [here](https://github.com/NCATS-Tangerine/cq-notebooks/wiki/St.-Judes-FA-Demonstrator).
  
**Data Types and Sources:**
1. Gene-ortholog associations from Panther, via SciGraph (BioLink [/bioentity/gene/{id}/homologs/](https://api.monarchinitiative.org/api/#!/bioentity/get_gene_homolog_associations))
2. Gene-protein associations from Ensembl, via SciGraph (BioLink API or Monarch API dynaimc cypher query?)
3. Functional annotations from GO, via SciGraph (Biolink API) or via Wikidata (SPARQL API)
  
**Sub-Queries/Tasks:**  
   
Input: NCBIGene identifiers for 11 FA-core genes
  1. Retrieve orthologes of FA-core genes  
  2. Retrieve proteins encoded by genes in this cross-species set  
  3. Retrieve GO terms annotated to these proteins  
  4. Execute similarity analysis that returns the set of similar proteins/genes across species  
  5. Retrieve genes that encode these proteins  
  6. Retrieve human orthologs of all non-human genes in this set 

Output: GeneSetQ2 (functionally similar human genes based on cross-species GO-similarity analysis)

--------

*Note that the subqueries above can be parameterized in any number of ways in their implementation (e.g. select specific taxa  for cross-species expansion, facet on a MF or BP or CC subset of GO annotations, set different threshholds for GO-based similarity, selecting different knowledge sources or routes to retrieve a particular data type). Different combinations of parameters can be explored using different notebooks in this directory.*


	

