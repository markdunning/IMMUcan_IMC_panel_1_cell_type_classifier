# IMMUcan_cell_type_classification_panel_1_public

## Background

In [IMMUcan](https://immucan.eu/) patient samples are collected from 2019 until August 2025 for multimodal analysis. Imaging Mass Cytometry is applied to all collected samples using two antibody panels. To identify cell phenotypes continuously over time we trained a random forest classifier on labelled single-cell data from a total of 179 images from 179 patients across 5 cancer indications (breast cancer,renal cell carcinoma, colorectal cancer, head and neck cancer, non-small cell lung cancer). The classifier is used to classify single-cell data from panel 1 for all patients within IMMUcan.

## Data
The data has been deposited at Zenodo: [data](https://zenodo.org/records/12912567): Once downloaded all data should be stored in one folder which can be used as the base folder to run all code in this repo.

The Zenodo repo contains the following:
- _sce_labelled_V1.rds_ a `SingleCellExperiment` object containing all labelled cells from the first batch of labelling
- _sce_labelled_V3.rds_ a `SingleCellExperiment` object containing all labelled cells from the second batch of labelling
- _rf_images_DCfix.rds_ the RF model which can be used for cell type predictions
- _sce_raw.rds_ a `SingleCellExperiment` object containing all cells from the 179 images
- __all_images.rds__ a `CytoImageList` object which contains all the images from all images
- __all_masks.rds__ a `CytoImageList` object which contains all single-cell segmentation masks from all images
- a zip archive `images_masks` containing the tiff images and masks from all 179 images

## Analysis
There are three scripts.
1. contains basic heatmap plots to investigate the marker expression on the labelled cells
2. contains code to train a random forest
3. loads the combined single cells, images and masks from all 179 patients on which the classifier has been run and can be used to visualize the cell phenotypes using either [cytomapper](https://www.bioconductor.org/packages/release/bioc/html/cytomapper.html) or [cytoviewer](https://www.bioconductor.org/packages/release/bioc/html/cytoviewer.html).

