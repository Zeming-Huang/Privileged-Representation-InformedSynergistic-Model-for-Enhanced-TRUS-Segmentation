# PRISM

Official implementation of **PRISM**: **Privileged Representation-Informed Synergistic Model for Enhanced TRUS Segmentation**.

## Abstract

Transrectal ultrasound (TRUS) segmentation is clinically important but remains challenging because TRUS images often exhibit low contrast, blurred anatomical boundaries, and substantial appearance variability. PRISM addresses this problem through a privileged-learning framework in which MRI is used as privileged information during training to guide feature learning, while deployment remains TRUS-only. Specifically, PRISM initializes both student and teacher branches from LiteMedSAM, aligns latent representations across modalities with an MMD-based distribution constraint, and performs cross-modal feature interaction through a synergistic learning module with adaptive feature fusion. At inference time, the MRI branch is removed, and the learned feature interaction is transferred into a uni-modal enhancement path so that the model preserves the benefits of privileged supervision without requiring MRI input. This design enables PRISM to improve TRUS segmentation quality while maintaining a practical deployment setting.

## Framework

<p align="center">
  <img src="assets/prism_framework.png" alt="PRISM framework" width="100%">
</p>
<p align="center"><em>PRISM training and inference framework.</em></p>

## Overview

This repository provides the core PRISM training, evaluation, and public reproduction pipeline:

- `train_dual_modal.py`: dual-modal training with privileged MRI guidance
- `inference.py`: TRUS-only public inference
- `evaluate.py`: unified segmentation evaluation

Compact reproduction notes are available in [docs/reproducibility.md](docs/reproducibility.md).

External assets for public reproduction are hosted here:

- [PRISM public assets](https://drive.google.com/drive/folders/1HHtXd_TIhhhL1EtGIESXpZqIY_LGxyML?usp=drive_link)

## License

This repository is released under the **Apache License 2.0**. See [LICENSE](LICENSE) for the full text.

## Acknowledgements

This project builds on and benefits from several important prior works and open-source efforts:

- We thank the **MedSAM / LiteMedSAM** authors for the medical adaptation of the Segment Anything framework and for the lightweight initialization used in this repository.
- **LUPI (Learning Using Privileged Information)** for the privileged-information learning paradigm that motivates PRISM's training strategy.
- The **MR to Ultrasound Registration for Prostate Challenge** dataset and related open resources for enabling reproducible prostate MRI-TRUS research.
- Open-source community efforts that make code, pretrained models, and research artifacts accessible for reproducible medical AI research.

## Citation

PRISM citation information will be added here when the paper metadata is finalized.
