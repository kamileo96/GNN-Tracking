# GNN-Tracking

## Track finding using GNN

Kamil Dutkiewicz, 2023

This is the effect of an internship done at the Institute of Nuclear Physics of the Polish Academy of Sciences (IFJ PAN), under prof. Marcin Wolter.

Original notebooks can be found on:
https://github.com/marcinwolter/Tracking_student2022

The primary function of the notebooks is to reconstruct 3D tracks from XZ and YZ data gathered from strip detectors. Simulated data can be found in the **data** directory.
Graph Neural Networks are used in an attempt to increase robustness and effectivness of the model, compared to classic seeding algorithms. The GNN works by classyfing edges between hits as either true or false, allowing for track finding.

The main notebook: **GNN_muonE_glued_fit.ipynb**
1)Recreates the functionality of the original notebooks, while trying to improve on code clarity
2)Adds 3D visualisation functionality
3)Trains a GNN and uses it to fit 2D tracks, afterwards glueing them together using info from stereo layers

An attempt to improve the quality of the fits, by performing the fit using information from all layers at once (finding a line that minimizes distance from all strips), was made in the notebook:
**GNN_muonE_combined_fit.ipynb**
Mainly due to outliers, this did not improve the quality of the fits.

In the data, trackID 1 corresponds to muon and 2 to electron. In some events noise appears as additional tracks. In previous notebooks this noise is not loaded, in:
**GNN_muonE_false_hits_v2.ipynb**
An attempt is made to increase the robustness of the GNN classifier.
Increasing the noisiness of the training data improves the models ability to deal with noisy events, but only to some degree.
