# Bioinformatics Resources project
This project was performed in the context of the Bioinformatics Resources project, held by Professor Romanel at the University of Trento.

This analysis is performed on a Lung Squamous Cell Carcinoma Dataset (extracted from the Cancer Genome Atlas), containing 62940 observations. 
After an initial filtering, the steps performed were:

**1. Differential Expression Analysis (edgeR package)**
- Case and control goups were first visualized through PCA, then up- and down-regulated genes were highlighted in a Volcano plot and in a heat map.

**2. Gene set enrichment analysis (clusterProfiler package)**
- A Gene Ontology enrichment analysis was perfomred on both up- and down-regulated genes based on Biological Process and Molecular Function. A KEGG Pathway Enrichment was also conducted.

**3. Identify which TFs have enriched scores in the promoters of up-regulated genes**
- The 10 Transcription Factors whose motifs had the most enriched scores in the promoters of all up-regulated genes were extracted.

**4. Motif Enrichment**
- An enriched Transcription Factor (NRL) was selected and empirical distributions of scores for all PWMs found in MotifDB were extracted. For all of
them, the distribution threshold cutoff at 99.75% was computed.

**5. Pattern matching**
- Up-regulated genes having a region in their promoter with binding scores above the computed thresholds for any of the previously selected PWMs were identified. The best pattern match was then plotted.

**6. STRING intercations**
- The STRING webtool was employed to visualize and extract protein-protein interactions among DEGs.

**7. Network Analysis (igraph package)**
- The network was imported in R and the largest connected component was identified for both up- and down-regulated genes.

**Conclusions:**

In first place, we were able to correctly distinguish between Cases and Controls in the preliminary analyses. Then, the enrichment analysis of up-regulated genes showed a prevalence of genes that partake in the cell cycle, suggesting a possible disruption (and up-regulation) that is common in tumors and metastases. On the other hand, looking at the down-regulated ones we see effects on the immune system and chemotaxis, that could be attributable to tumor cells developing mutations to avoid detection. Regarding motif enrichment analysis, some common motifs in the promoters of our up-regulated genes were found. Finally, the network analysis confirmed our previous enrichment results.

