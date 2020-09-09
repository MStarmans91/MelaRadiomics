# MelaRadiomics
Script to compute the features used in the paper "The BRAF p.V600E mutation of melanoma lung metastases cannot be discriminated on computed tomography through visual scoring or radiomics and machine learning." L. Angus, M. P. A. Starmans et al.

Before trying out the code in this repository, we advice you to get
familiar with the WORC package through the WORC tutorial:
https://github.com/MStarmans91/WORCTutorial.

## Installation
For the feature extraction, only the PREDICT package, at least version 3.1.10,
and the subsequent dependencies are required, which can be installed through pip:

    pip install "PREDICT>=3.1.10"

For the model optimization, additionally WORC, version 3.3.2, is required:

    pip install "WORC==3.3.2"

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

## Known Issues
For some of the known issues, please visit the WORC FAQ:
https://worc.readthedocs.io/en/latest/static/faq.html.
