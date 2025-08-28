# Cancer RNA-seq Analysis Pipeline

This repository contains a comprehensive pipeline for the analysis of cancer RNA-seq data, including differential gene expression, functional enrichment, and machine learning-based drug response prediction. The workflow is implemented in R and R Markdown, leveraging state-of-the-art Bioconductor packages and statistical methods.

## Repository Structure

- `Trabalho_Grupo3_Final.rmd` / `Trabalho_Grupo3_Final.html`: Main R Markdown analysis pipeline and its rendered HTML output.
- `Trabalho_Grupo3.rmd` / `Trabalho_Grupo3.html`: Alternate or earlier version of the analysis pipeline.
- `CCLE_mutations.csv` / `CCLE_mutations.zip`: Mutation data from the Cancer Cell Line Encyclopedia (CCLE).
- `CCLE_RNAseq_reads.csv` / `CCLE_RNAseq_reads.zip`: RNA-seq read counts from CCLE.
- `primary-screen-replicate-collapsed-logfold-change.csv`: Drug response data (log fold change).
- `sample_info.xlsx`: Sample metadata and annotations.
- `README.md`: This file.

## Main Features

### 1. Data Preprocessing
- Import and clean RNA-seq and mutation data.
- Integrate sample metadata.
- Filter and normalize expression matrices.
- Robust extraction of ENSEMBL gene IDs for downstream analysis.

### 2. Differential Expression Analysis
- Use `limma` and `edgeR` for differential gene expression analysis.
- Support for multiple biological contrasts (e.g., primary vs. metastasis, mutation count groups).
- TREAT thresholding for robust significance assessment.

### 3. Functional Enrichment
- Annotate significant genes using `gprofiler2`.
- Perform Gene Ontology (GO) and pathway enrichment analysis.
- Only valid ENSEMBL IDs are used for enrichment to ensure compatibility and accuracy.

### 4. Machine Learning
- Predict drug response using gene expression and mutation features.
- Use `caret` for model training and cross-validation.
- Error handling for missing variables and robust data preparation.

## How to Use

1. **Install Required Packages**
	- R (>= 4.0 recommended)
	- Bioconductor packages: `limma`, `edgeR`, `gprofiler2`, `caret`, `FactoMineR`, etc.
	- Install packages using:
	  ```R
	  if (!requireNamespace("BiocManager", quietly = TRUE))
			install.packages("BiocManager")
	  BiocManager::install(c("limma", "edgeR", "gprofiler2", "FactoMineR"))
	  install.packages("caret")
	  ```

2. **Run the Analysis**
	- Open `Trabalho_Grupo3_Final.rmd` in RStudio or VS Code.
	- Knit the document to generate the HTML report.
	- Ensure all data files are present in the repository root.

3. **Customize Contrasts and Parameters**
	- Modify the R Markdown file to change biological contrasts or analysis parameters as needed.

## Data Sources
- Cancer Cell Line Encyclopedia (CCLE): https://portals.broadinstitute.org/ccle
- Drug response and sample metadata: Provided in repository files.

## Output
- Differential expression tables and plots.
- GO and pathway enrichment results.
- Machine learning model performance metrics and predictions.
- Comprehensive HTML report summarizing all analyses.

## Troubleshooting
- Ensure all required R packages are installed.
- Check that all data files are present and paths are correct.
- If you encounter errors about missing variables (e.g., `drug`), ensure code chunks are run in the correct order.

## License
This repository is for academic and research use. Please cite appropriately if you use or adapt this pipeline.

## Contact
For questions or contributions, please open an issue or contact the repository owner.
