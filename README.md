# Single-Cell RNA-Seq Analysis Workshop

A hands-on guide to scRNA-seq analysis covering QC, differential expression, pathway enrichment, and cell type annotation.

## Analysis Pipeline

| Module | Description |
|--------|-------------|
| **01_qc_pre_processing.qmd** | Quality control, filtering, normalization, dimensionality reduction |
| **02_dea_pea.qmd** | Differential expression and pathway enrichment (GO, KEGG) |
| **03_cell_type_annotation.qmd** | Cell type annotation with CyteTypeR, SingleR, GPTCelltype |

## Directory Structure

```
.
├── scripts/           # Analysis pipelines (this directory)
├── read/              # Input datasets
├── write/
│   ├── figures/       # Output plots
│   └── tables/        # Output tables
└── checkpoints/       # Intermediate Seurat objects
```

## Prerequisites

### Software

- R (>= 4.2.0)
- RStudio
- Quarto

### R Packages

```r
# CRAN
install.packages(c(
  "tidyverse",
  "Seurat",
  "SeuratData",
  "devtools",
  "conflicted",
  "patchwork",
  "pheatmap",
  "tictoc"
))

# GitHub
devtools::install_github("wolf5996/BadranSeq")
devtools::install_github("NygenAnalytics/CyteTypeR")

# Bioconductor
BiocManager::install(c(
  "SingleR",
  "celldex",
  "clusterProfiler",
  "org.Hs.eg.db",
  "enrichplot"
))
```

## Data

Uses the **IFNB stimulation dataset** from SeuratData - PBMCs comparing control vs IFN-beta stimulated cells.

```r
SeuratData::InstallData("ifnb")
```

## Getting Started

1. Open `scrna_seq_analysis.Rproj` in RStudio
2. Install required packages
3. Render QMD files in order (01 → 02 → 03)

## Key Tools

| Tool | Purpose |
|------|---------|
| **Seurat** | scRNA-seq analysis framework |
| **BadranSeq** | Publication-ready visualizations |
| **CyteTypeR** | API-based cell type annotation |
| **SingleR** | Reference-based annotation |
| **clusterProfiler** | Pathway enrichment |

## Author

**Dr Badran Elshenawy**
