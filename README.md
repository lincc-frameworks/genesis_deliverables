# genesis_deliverables

## Milestones
- **Milestone 1**: Catalog Availability (Month 1; objective 1a)   
Definition: Initial (tabular) catalog data is hosted in HATS format on the American Science
Cloud.  
Quantitative Metrics: Data sets are available to science community.

- **Milestone 2:** HATS Single Image Cutouts and Spectra (Month 2; objective 1a).   
Definition: A working prototype of a HATS catalog storing single image cutouts and spectra
for each object.  
Quantitative Metrics: Multi-modal data set for at least 100,000 objects is
available on the American Science Cloud. The team demonstrates the use with an example
analysis notebook.

- **Milestone 3:** HATS Multi Image Cutouts and Spectra (Month 6; objective 1a).   
Definition: A working prototype of a HATS catalog storing both multiple image cutouts and
spectra for each entry.   
Quantitative Metrics: User can query data set for a time series of
image stamps or spectra. The team demonstrates the use with an example notebook and via
the model training from milestone 4.

- **Milestone 4:** Cross-Modal Data Loader (Month 6; objective 1a).   
Definition: A data loader API that allows the training of PyTorch models from multi-
modal HATS catalogs; throughput characterization report.  
Quantitative Metrics: The team demonstrates training ML models from multiple modalities, and provides an example
notebook.

- **Milestone 5:** Federated Data Access (Month 6; objective 1b).   
Definition: A collection-dataset mechanism supports transparent aggregation across remote
stores.  
Quantitative Metrics: User can query the main catalog from one location and receive
(e.g., images and spectra) extensions from another.

- **Milestone 6:** Tokenized Data as a Modality (Month 7; objective 1a).   
Definition: A working prototype of HATS table extensions storing tokenized representations
of imaging, spectroscopic, and scalar data, produced using published Polymathic AI tokenizers
(AION-1 and the universal spectral tokenizer), accessible through LSDB alongside
other modalities.  
Quantitative Metrics: Tokenized extensions are available for ≥ 108 objects
across at least two imaging surveys and one spectroscopic survey. The team uses the data to
retrieve tokens for a set of objects via an LSDB query and provides an example notebook.

- **Milestone 7:** Multimodal Training via LSDB (Month 9; objective 2 ).   
Definition: A demonstration that LSDB spatial cross-matching on tokenized HATS extensions
streams aligned cross-modal token sequences into a training loop at a rate sufficient to train
an AION-1-style multimodal masked-modeling transformer.   
Quantitative Metrics: The team trains such a foundation model on cross-matched tokenized data spanning at least two imaging
surveys and one spectroscopic survey, with the training loop remaining GPU-bound on a
single Perlmutter node, and provides an example notebook.

## Decision Gates
- **DG1.** Multi-modal data access and throughput.  
Metric: Retrieval of multi-modal data using a 60 arcsecond cone search is comparable (within
50% wall clock time) to a current tabular-only LSDB catalog query.   
Rationale: Demonstrate that the infrastructure can provide a single point of access to multi-modal data that will
unlock new statistical analyses and machine learning models.

- **DG2.** Federated Data Access.  
Metric: LSDB query can retrieve the core data from one location and join auxiliary data at a
separate location.  
Rationale: Demonstrate that the infrastructure can enable model training
without all data centralized at a single location.

- **DG3.** Multimodal Foundation Model Training.  
Metric: Production of a AstroCLIP or AION-like open-source multimodal foundation model,
trained through our Unified Multimodal Data Service on DESI spectra, and DES and
Rubin DP2 imaging.  
Rationale: Demonstrates how the work straightforwardly enables new
end-to-end workflows for training DOE Cosmic Frontier foundation models.
