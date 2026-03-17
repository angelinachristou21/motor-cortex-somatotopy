Motor Cortex Somatotopic Mapping — fMRI Analysis
A neuroimaging analysis project conducted as part of the Brain Imaging course at Vrije Universiteit Amsterdam (VU). The project investigates the somatotopic organisation of body-part representations in the human motor and somatosensory cortex, using 7T fMRI data and a General Linear Model (GLM).
---

## Overview

The brain's motor cortex contains a spatial map of the body — the so-called *motor homunculus* — where different body parts are represented in distinct cortical locations. This project analyses a somatotopic motor-mapping experiment to recover and visualise these representations from BOLD fMRI signals.

Subjects watched a movie of an avatar performing movements of facial muscles, fingers, hands, and legs in a quasi-cyclic order. A GLM was fitted to estimate the BOLD response for each body-part condition, and the resulting beta maps were visualised as cortical flatmaps. The analysis focuses on the motor (area S3a) and somatosensory (area S1) regions along the central sulcus.

---

## Key Analyses

- **Lateralised contrasts** — left vs. right hand and leg activation, verifying contralateral motor organisation
- **Face vs. baseline** — mapping activation for individual facial muscles (eyebrows, eyes, mouth, tongue)
- **Finger-to-finger contrasts** — testing whether individual fingers produce spatially distinct activations
- **Body-part domination maps** — identifying, per vertex, which body part elicits the strongest response

---

## Repository Structure

```
├── Group_39.ipynb       # Main analysis notebook
└── README.md
```

---

## Data

The fMRI data are publicly available on [figshare](https://figshare.com/articles/dataset/fMRI_Teaching_Materials/14096209).

The dataset includes:
- Surface-projected BOLD signals averaged across 5 runs for a single subject
- Acquired at 7 Tesla
- Cortical surfaces from the Human Connectome Project (`hcp_999999`)
- HCP multi-modal parcellation atlas (Glasser et al., 2016) for region-of-interest selection
- BIDS-formatted `events.tsv` files describing the experimental timing

---

## Dependencies

### Python packages

```bash
pip install nibabel nilearn
pip install git+https://github.com/gallantlab/pycortex.git#egg=pycortex
```

### System dependency (Ubuntu/Debian)

```bash
apt install inkscape
```

---

## Running the Notebook

The notebook is designed to run on **Google Colab**, where it will automatically download all required data from figshare.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO/blob/main/Group_39.ipynb)

> Replace `YOUR_USERNAME/YOUR_REPO` with your actual GitHub username and repository name.

---

## Results Summary

- Hand and leg activation showed the expected contralateral lateralisation, with hand regions clearly delineated in S3a and S1.
- Facial muscle movements (especially tongue and mouth) produced large activation extending into the putamen, consistent with prior literature.
- Finger-to-finger contrasts showed stronger overall activation for the left hand.
- Body-part domination maps revealed no strictly monotonic somatotopic gradient, suggesting the discrete muscle conditions do not fully tile the motor cortex continuously.

---

## References

- Zeharia, N., Hertz, U., Flash, T., & Amedi, A. (2015). New whole-body sensory-motor gradients revealed using phase-locked analysis and verified using multivoxel pattern analysis and functional connectivity. *Journal of Neuroscience*, 35(7), 2845–2859.
- Saadon-Grosman, N., Loewenstein, Y., & Arzy, S. (2020). The 'creatures' of the human cortical somatosensory system. *Brain Communications*, 2(1), fcaa003.
- Penfield, W., & Boldrey, E. (1937). Somatic motor and sensory representation in the cerebral cortex of man as studied by electrical stimulation. *Brain*, 60, 389–443.
- Glasser, M. F., et al. (2016). A multi-modal parcellation of human cerebral cortex. *Nature*, 536, 171–178.
- Dumoulin, S. O., & Wandell, B. A. (2008). Population receptive field estimates in human visual cortex. *NeuroImage*, 39(2), 647–660.
