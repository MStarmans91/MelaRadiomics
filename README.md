[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4644067.svg)](https://doi.org/10.5281/zenodo.4644067)

# MelaRadiomics
Script to compute the features used in the paper "The BRAF P.V600E Mutation Status of Melanoma Lung Metastases Cannot Be Discriminated on Computed Tomography by LIDC Criteria nor Radiomics Using Machine Learning." by L. Angus and M. P. A. Starmans et al. 2021.

Before trying out the code in this repository, we advice you to get
familiar with the WORC package through the WORC tutorial:
https://github.com/MStarmans91/WORCTutorial.

## License
This package is covered by the open source [APACHE 2.0 License](APACHE-LICENSE-2.0).

When using this code, please cite this repository and the corresponding paper
as following:

``Starmans, M.P.A. MelaRadiomics. Zenodo (2021). Available from: https://github.com/MStarmans91/MelaRadiomics, DOI: https://doi.org/10.5281/zenodo.4644067.``

``Angus, L.; Starmans, M.P.A.; Rajicic, A.; Odink, A.E.; Jalving, M.; Niessen, W.J.; Visser, J.J.; Sleijfer, S.; Klein, S.; van der Veldt, A.A.M. The BRAF P.V600E Mutation Status of Melanoma Lung Metastases Cannot Be Discriminated on Computed Tomography by LIDC Criteria nor Radiomics Using Machine Learning. J. Pers. Med. 2021, 11, 257. https://doi.org/10.3390/jpm11040257. ``


## Installation
For both the feature extraction and model optimization, WORC, version 3.3.3,
is required:

    pip install "WORC==3.3.3"

## Usage: Feature Extraction
The ExtractFeatures.py script can be used to extract all features. We provided
you with the exact same configuration file that was used in the study. The
script can be easily modified to use your own data instead of the
provided example data and requires:

1. An image in ITK Image format, e.g. .nii, .nii.gz, .tiff, .nrrd, .raw
2. A segmentation in ITK Image format.
3. Optionally, metadata in DCM format

Extracting the features from the example data should take less than 10 seconds.
Using a larger image and/or mask may result in a longer computation time.

## Usage: Model Optimization
The ModelOptimization.py script can be used for the model optimization. Again,
we provided you with the exact same configuration file that was used in the study.
The script can be easily modified to use your own data instead of the
provided example data and requires: see for more details the script itself.

Note that the script performs a dummy experiment: it supplies 10x the example
features to WORC, which will result in non-separable dataset, and thus no
sensible model. Usage of your own data is therefore highly recommended.

## Hyperparameter values of best workflows
For each of the five models described in the paper, in the SelectedWorkflows
folder, .csv files with the values of the hyperparameters for the top 50
performing workflows as included in the ensemble are used. As some
hyperparameters are fixed in the default options of the WORC package,
there are files including the values for all hyperparameters and only those
with more than one unique value.

## Known Issues
For some of the known issues, please visit the WORC FAQ:
https://worc.readthedocs.io/en/latest/static/faq.html.
