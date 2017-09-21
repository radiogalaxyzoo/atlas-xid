# Machine learning methods for radio source host galaxy cross-identification

M.A. Alger, J.K. Banfield, C.S. Ong, O.I. Wong, L.Rudnick, R.P. Norris

_submitted to Monthly Notices of the Royal Astronomical Society: day-month-year_

![RGZ avatar]({{ site.url }}/assets/radiogzavatar.png)

### Abstract
We consider the problem of determining the infrared host galaxies of radio emissions detected
in wide-area radio surveys. We propose a method for reducing the cross identification task to
binary classification, a standard machine learning task. Binary classification is well under-
stood and well supported by machine learning software. We test our methods on the radio
sources detected in the 1.4 GHz Australia Telescope Large Area Survey (ATLAS) observa-
tions of the Chandra Deep Field - South (CDFS) and the ESO Large Area ISO Survey - South
1 (ELAIS-S1) fields, and cross identify them with Spitzer Wide-area Infrared Extragalactic
survey (SWIRE). We compared two categories of labels: expert cross-identifications of CDFS
from the initial ATLAS data release and crowdsourced cross-identifications of CDFS from
Radio Galaxy Zoo. Our empirical results show that the cross-identification accuracy of the
predictor trained on Radio Galaxy Zoo labels is comparable to the predictor trained on expert
labels, demonstrating the value of crowdsourced labels. In addition to cross validation per-
formance on CDFS, we demonstrate that our method also generalizes to ELAIS-S1. Cross-
identification performance with our method is limited by a lack of radio morphology inform-
ation as our method for reducing cross identification to binary classification require that radio
sources are isolated from other sources. This assumption breaks down particularly with high
surface brightness sensitivity surveys. We suggest that source identifications and radio mor-
phology information would resolve this problem.

