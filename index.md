# Machine learning methods for radio source host galaxy cross-identification

M.&nbsp;J.&nbsp;Alger, J.&nbsp;K.&nbsp;Banfield, C.&nbsp;S.&nbsp;Ong, L.&nbsp;Rudnick, O.&nbsp;I.&nbsp;Wong, C.&nbsp;Wolf, H.&nbsp;Andernach, R.&nbsp;P.&nbsp;Norris, S.&nbsp;S.&nbsp;Shabala

_submitted to Monthly Notices of the Royal Astronomical Society: day-month-year_

## Abstract

We consider the problem of determining the host galaxies of radio sources by
  cross-identification. This has traditionally been done by eye and expert
  judgement, a method that will be intractable for wide-area radio surveys
  like the Evolutionary Map of the Universe (EMU). Automated
  cross-identification will be critical for these future surveys, and machine
  learning may provide the tools to develop such methods. We apply a standard
  approach from computer vision to cross-identification, introducing one
  possible way of automating this problem, and explore the pros and cons of
  this approach. We apply our method to the 1.4&nbsp;GHz Australian Telescope
  Large Area Survey (ATLAS) observations of the *Chandra* Deep Field
  South (CDFS) and the ESO Large Area ISO Survey South 1 (ELAIS-S1) fields by
  cross-identifying them with the *Spitzer* Wide-area Infrared
  Extragalactic (SWIRE) survey. We train our method with two sets of
  data: expert cross-identifications of CDFS from the initial ATLAS data
  release and crowdsourced cross-identifications of CDFS from Radio Galaxy
  Zoo. We found that a simple strategy of cross-identifying a radio component
  with the nearest galaxy performs comparably to our more complex machine learning methods, though our estimated best-case performance is near 100 per cent.
  ATLAS contains 87 complex radio sources that have been cross-identified by experts,
  so our method does not see enough
  complex examples to learn how to cross-identify them accurately. Much larger
  datasets are therefore required for training methods like ours. We also show
  that training our method on Radio Galaxy Zoo cross-identifications gives
  comparable results to training our method on expert cross-identifications,
  demonstrating the value of crowdsourced training data.

### Appendix C: SWIRE Object Scores

In Table C1 and Table C2 we list the scores for each SWIRE infrared object in CDFS and ELAIS-S1 respectively.

- Table C1: Scores output by our trained classifiers for SWIRE&nbsp;CDFS candidate host galaxies.
- Table C2: Scores output by our trained classifiers for SWIRE&nbsp;ELAIS-S1 candidate host galaxies.

### Appendix D: ATLAS Component Cross-identifications

In Table D1 and Table D2 we list the SWIRE cross-identifications of each ATLAS radio component in CDFS and ELAIS-S1 respectively.

- Table C1: Cross-identifications for ATLAS&nbsp;CDFS components.
- Table C2: Cross-identifications for ATLAS&nbsp;ELAIS-S1 components.

### Appendix E: Cross-identification figures

Figure E1 (a)&ndash;(ra) shows cross-identifications of resolved sources. As an example of the full set of figures, we show Figure E1(qy).

**Figure E1(qy)**

![Figure E1(qy)](/atlas-xid/assets/example_sorted_467_186.pdf.png)

## Running the Experiments

1. Clone `chengsoonong/crowdastro` and `chengsoonong/crowdastro-projects`.
2. Edit `crowdastro/crowdastro/crowdastro.json` to point to the data files. Run `python3 -m crowdastro.import_data --ir swire` to import the SWIRE and ATLAS datasets. This results in `crowdastro.h5`, and so can be skipped if you already have this file.
3. Run `crowdastro/notebooks/100_radio_table.ipynb` to build `one-table-to-rule-them-all.tbl`, which is a cross-identified table of the three ATLAS catalogues.
4. Edit `crowdastro-projects/scripts/pipeline.py` to point to the data paths, then run it. This produces all prediction and cross-identification output files.
