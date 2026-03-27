# mgnify-protein-ssn-prototype
This repo contains functional poof-of-concept for mapping  10M-protein into a biome-integrated Sequence Similarity Network (SSN). Validates MMseqs2 alignment logic and metadata-integrated graph topology for MGnify

##  Project Overview
The pipeline transforms raw protein sequences into a navigable functional landscape. By correlating sequence similarity with environmental metadata, I enable the discovery of biome-specific protein clusters and evolutionary transitions.

##  Prototype Results (Logic Validation)
To verify the alignment-to-visualization flow, a 500-sequence subset from UniProt was used as a proxy. 
* **Engine:** MMseqs2 (All-vs-all alignment).
* **Thresholds:** E-value < 10⁻⁵, bitscore filtering.
* **Output:** Node/Edge tables compatible with WebGPU-accelerated rendering.

### Visualization Proof-of-Concept
![SSN Visualization](./images/visualization.png)
*Figure 1: SSN prototype showing functional clustering. Distance correlates to similarity; colors represent biomes.*

##  Scalability Strategy
While this prototype uses Pandas and standard TSVs, the 10M production run will implement:
1. **Apache Parquet:** Reducing disk footprint by 70%.
2. **Vectorized Partitioning:** Managing memory usage within 16GB-32GB RAM limits.
3. **MMseqs2 Linclust:** Reducing 10M sequences to ~1.5M representative nodes.

##  Content
* `notebooks/`: Pipeline logic from FASTA to Graph files.
* `outputs/`: Generated similarity tables and CSVs.
* `requirements.txt`: Environment dependencies.
