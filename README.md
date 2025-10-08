# Gene Expression Analysis Project

## Overview
This project performs comprehensive analysis of TCGA-PANCAN gene expression data to identify molecular signatures of different cancer types using unsupervised machine learning approaches.

## Project Structure

```
gene_expression/
├── notebooks/
│   ├── 1_preprocessing.ipynb           # Data loading, cleaning, and preprocessing
│   ├── 2_clustering_analysis.ipynb     # Unsupervised clustering and evaluation
│   ├── 3_cluster_interpretation.ipynb  # Gene analysis and interpretation
│   ├──exploration.ipynb               # Original analysis (legacy)
│   └── figures/
│       ├── cancer_type_distribution.png    # Sample distribution
│       ├── pca_visualization.png          # PCA plots
│       ├── clustering_comparison.png       # Cluster vs true labels
│       ├── confusion_matrix_heatmap.png   # Performance visualization
│       └── gene_expression_heatmaps.png   # Gene signature analysis
├── .gitignore
└──README.md

```

## Workflow

### 1. Data Preprocessing (`1_preprocessing.ipynb`)
- **Input**: Raw TCGA-PANCAN tar.gz file
- **Process**: 
  - Extract and load gene expression data and cancer labels
  - Merge datasets and perform quality checks
  - Apply StandardScaler for feature normalization
  - Use VarianceThreshold for feature selection
- **Output**: Clean, preprocessed data ready for analysis

### 2. Clustering Analysis (`2_clustering_analysis.ipynb`)
- **Input**: Preprocessed gene expression data
- **Process**:
  - PCA visualization of data structure
  - Elbow method for optimal cluster selection
  - K-Means clustering with quality evaluation
  - Comprehensive performance metrics
- **Output**: Cluster assignments and evaluation results

### 3. Cluster Interpretation (`3_cluster_interpretation.ipynb`)
- **Input**: Clustering results and preprocessed data
- **Process**:
  - Identify discriminant genes for each cluster
  - Analyze gene expression patterns
  - Create biological interpretation of clusters
  - Generate visualization of gene signatures
- **Output**: Biological insights and gene-level analysis

## Key Results

- **Dataset**: 801 tumor samples, 5 cancer types (BRCA, KIRC, LUAD, PRAD, COAD)
- **Features**: ~20,000 genes after variance filtering
- **Clustering Performance**: 
  - Adjusted Rand Index: ~0.80 (excellent agreement with true labels)
  - Overall accuracy: 80-99% depending on cancer type
- **Biological Insights**: Each cancer type has distinct molecular signatures

## Cancer Types
- **BRCA**: Breast invasive carcinoma
- **KIRC**: Kidney renal clear cell carcinoma  
- **LUAD**: Lung adenocarcinoma
- **PRAD**: Prostate adenocarcinoma
- **COAD**: Colon adenocarcinoma

## Requirements
```python
pandas
numpy
scikit-learn
matplotlib
seaborn
```

## Usage

1. **Start with preprocessing**:
   ```bash
   jupyter notebook notebooks/1_preprocessing.ipynb
   ```

2. **Perform clustering analysis**:
   ```bash
   jupyter notebook notebooks/2_clustering_analysis.ipynb
   ```

3. **Interpret results**:
   ```bash
   jupyter notebook notebooks/3_cluster_interpretation.ipynb
   ```

## Key Findings

1. **Molecular Distinction**: Different cancer types have unique gene expression signatures
2. **Clustering Success**: Unsupervised methods can identify cancer types with high accuracy
3. **Biomarker Discovery**: Identified key discriminant genes for each cancer type
4. **Clinical Relevance**: Results support molecular-based cancer classification approaches

## Next Steps

- Supervised learning for cancer type prediction
- Pathway analysis of discriminant genes
- Validation on independent datasets
- Investigation of potential therapeutic targets

## Data Source

The Cancer Genome Atlas (TCGA) Pan-Cancer analysis project  
- Original data: TCGA-PANCAN-HiSeq-801x20531  
- 801 samples across 5 major cancer types  
- RNA-Seq gene expression profiles

## Citations / Acknowledgements

If you use this dataset, please cite:

The original dataset (hosted at [Synapse:syn4301332](https://www.synapse.org/#!Synapse:syn4301332)) is maintained by The Cancer Genome Atlas Pan-Cancer Analysis Project.
