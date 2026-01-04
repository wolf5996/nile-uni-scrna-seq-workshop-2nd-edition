# Nile University Bioinformatics Workshop (2nd Edition)

**January 3-4, 2026**

A comprehensive workshop on single-cell RNA sequencing (scRNA-seq) analysis, covering fundamental concepts through hands-on computational analysis.

## Workshop Schedule

| Day | Focus | Content |
|------------------|------------------------|------------------------------|
| **Day 1** | Introductory Talk | Overview of scRNA-seq technology, experimental design, and biological applications |
| **Day 2** | Hands-on Workshop | Computational analysis pipeline from raw data to biological interpretation |

## Repository Structure

```         
.
├── talk/                          # Day 1 presentation materials
└── workshop/
    ├── r_fundamentals/            # R programming basics
    │   ├── read/                  # Input data
    │   ├── write/
    │   │   ├── figures/           # Output plots
    │   │   └── tables/            # Output tables
    │   ├── scripts/               # R scripts and QMD files
    │   └── checkpoints/           # Intermediate R objects
    └── scrna_seq_analysis/        # Main scRNA-seq analysis
        ├── read/                  # Input datasets
        ├── write/
        │   ├── figures/           # Analysis figures
        │   └── tables/            # Analysis tables
        ├── scripts/               # Analysis pipelines
        └── checkpoints/           # Seurat objects
```

## Workshop Modules

### R Fundamentals (`workshop/r_fundamentals/scripts/`)

-   **tidyverse_fundamentals.qmd** - Comprehensive R/tidyverse tutorial covering data manipulation, visualization, and analysis pipelines

### scRNA-seq Analysis (`workshop/scrna_seq_analysis/scripts/`)

| Module | Description |
|----------------------------|--------------------------------------------|
| **01_qc_pre_processing.qmd** | Quality control, filtering, normalization, and dimensionality reduction |
| **02_dea_pea.qmd** | Differential expression analysis and pathway enrichment (GO, KEGG) |
| **03_cell_type_annotation.qmd** | Automated cell type annotation using CyteTypeR, SingleR, GPTCelltype, and manual marker-based approaches |

## Prerequisites

### Software Requirements

-   R (\>= 4.2.0)
-   RStudio
-   Quarto

### R Packages

``` r
# CRAN packages
install.packages(c(
  "tidyverse",
  "Seurat",
  "devtools",
  "conflicted",
  "patchwork",
  "pheatmap",
  "tictoc"
))

# GitHub packages
devtools::install_github("wolf5996/BadranSeq")
devtools::install_github("NygenAnalytics/CyteTypeR")

# Bioconductor packages
BiocManager::install(c(
  "SingleR",
  "celldex",
  "clusterProfiler",
  "org.Hs.eg.db",
  "enrichplot"
))
```

## Getting Started

1.  Clone the repository
2.  Open the `.Rproj` file in RStudio
3.  Install required packages (see above)
4.  Navigate to the `scripts/` directory
5.  Render QMD files in order (01, 02, 03)

## Data

The workshop uses the **IFNB stimulation dataset** from the SeuratData package - a PBMC dataset comparing control and IFN-beta stimulated cells.

``` r
# Install and load dataset
install.packages("SeuratData")
SeuratData::InstallData("ifnb")
```

## Key Analysis Tools

| Tool                | Purpose                          |
|---------------------|----------------------------------|
| **Seurat**          | scRNA-seq analysis framework     |
| **BadranSeq**       | Publication-ready visualizations |
| **CyteTypeR**       | API-based cell type annotation   |
| **SingleR**         | Reference-based annotation       |
| **clusterProfiler** | Pathway enrichment analysis      |

## Author

**Dr Badran Elshenawy**

## License

This workshop material is provided for educational purposes.