# Machine learning methods for radio source host galaxy cross-identification

M.&nbsp;J.&nbsp;Alger, J.&nbsp;K.&nbsp;Banfield, C.&nbsp;S.&nbsp;Ong, O.&nbsp;I.&nbsp;Wong, L.&nbsp;Rudnick, R.&nbsp;P.&nbsp;Norris

_submitted to Monthly Notices of the Royal Astronomical Society: day-month-year_

## Abstract

Radio source host galaxy cross-identification is the problem of determining the host galaxies of radio sources detected in wide-area radio surveys. We propose a method for reducing the cross identification task to the standard machine learning task of binary classification. We apply our methods to the 1.4&nbsp;GHz Australian Telescope Large Area Survey (ATLAS) observations of the *Chandra* Deep Field South (CDFS) and the ESO Large Area ISO Survey South 1 (ELAIS-S1) fields, cross-identifying them with the *Spitzer* Wide-area Infrared Extragalactic survey (SWIRE). We compare two sets of training data: expert cross-identifications of CDFS from the initial ATLAS data release and crowdsourced cross-identifications of CDFS from Radio Galaxy Zoo. Our results show that the cross-identification accuracy of the predictor trained on Radio Galaxy Zoo cross-identifications is comparable to the predictor trained on expert cross-identifications, demonstrating the value of crowdsourced training data.

## Supplementary Material

### Appendix A: Tables of Accuracies

In Table A1 and Table A3 we list the balanced accuracies of classifiers on the galaxy classification task for CDFS and ELAIS-S1 respectively, averaged over each quadrant. In Table A2 and Table A4 we list the accuracies of our method on the cross-identification task for CDFS and ELAIS-S1 respectively, averaged over each quadrant.

- Table A1: Performance on the galaxy classification task for CDFS
- Table A2: Performance on the cross-identification task for CDFS
- Table A3: Performance on the galaxy classification task for ELAIS-S1
- Table A4: Performance on the cross-identification task for ELAIS-S1

### Appendix B: Tables of Predictions

In Table B1 and Table B3 we list the predicted class probabilities for each SWIRE infrared object in CDFS and ELAIS-S1 respectively. In Table B2 and Table B3 we list the predicted cross-identifications for each ATLAS DR1 radio component in CDFS and ELAIS-S1 respectively.

- Table B1: Predicted class probabilities for CDFS
- Table B2: Predicted cross-identifications for CDFS
- Table B3: Predicted class probabilities for ELAIS-S1
- Table B4: Predicted cross-identifications for ELAIS-S1

## Running the Experiments

1. Clone `chengsoonong/crowdastro` and `chengsoonong/crowdastro-projects`.
2. Edit `crowdastro/crowdastro/crowdastro.json` to point to the data files. Run `python3 -m crowdastro.import_data --ir swire` to import the SWIRE and ATLAS datasets. This results in `crowdastro.h5`, and so can be skipped if you already have this file.
3. Run `crowdastro/notebooks/100_radio_table.ipynb` to build `one-table-to-rule-them-all.tbl`, which is a cross-identified table of the three ATLAS catalogues.
4. Edit `crowdastro-projects/scripts/pipeline.py` to point to the data paths, then run it. This produces all prediction and cross-identification output files.
