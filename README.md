# mgnify-protein-ssn-prototype
This repo contains functional poof-of-concept for mapping  10M-protein into a biome-integrated Sequence Similarity Network (SSN). Validates MMseqs2 alignment logic and metadata-integrated graph topology for MGnify

##  Project Overview
The pipeline transforms raw protein sequences into a navigable functional landscape. By correlating sequence similarity with environmental metadata, I enable the discovery of biome-specific protein clusters and evolutionary transitions.

##  Quick Start
1.  Open the [ notebook](./notebooks/Prototype_with_500proteins.ipynb) to see the full pipeline, from environment setup to MMseqs2 execution.
2. The [output directory](./outputs/) contains the raw similarity tables and processed CSVs ready for WebGPU rendering.
3.  A static visualization of the 500-protein cluster is available in [images/visualization.png](./images/visualization.png).

##  Pipeline Highlights
* Alignment: Uses MMseqs2 for all-vs-all sequence comparison.
* Filtering: Nodes are connected based on a bitscore/E-value thresholding logic.
* Scalability: The workflow is designed to transition from this 500-seq prototype to a 10M-seq production run using Apache Parquet and Cosmograph.

*Note: This prototype utilizes a UniProt subset to validate logic while MGnify API optimizations are finalized.* 
