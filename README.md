# LC3 Recruitment Analysis

This JIPipe workflow quantifies LC3 recruitment around swollen *Aspergillus fumigatus* conidia associated with human monocytes. The dataset contains brightfield, FITC, and LC3 images from three independent donors, with 34 untreated and 40 GSK-treated images.

1. **Detect conidia.** TrackMate detects FITC-labeled conidia using a Difference of Gaussian spot detector. Spots with a mean FITC intensity below 30,000 are excluded. An 11-pixel dilation defines a ring around each retained conidium.
2. **Segment and match monocytes.** Cellpose 4 SAM segments monocytes from brightfield images. Each conidium is assigned to the monocyte with the greatest overlap with its outer ring. Only overlapping pairs are analyzed.
3. **Quantify LC3 recruitment.** For each matched conidium, divide the mean LC3 intensity in its ring by the mean LC3 intensity in the associated monocyte. Python scripts support downstream analysis and visualization.

**Raw images** are available on [Zenodo](https://doi.org/10.5281/zenodo.20797827).
