# CoMusion-GAN (work in progress)

End-semester computer vision project for human motion forecasting. The planned method combines CoMusion's Transformer–diffusion generator with kinematic losses and a history-conditioned temporal GAN discriminator. **The combined model has not yet been fully trained or evaluated.**

## Current stage

The Kaggle notebooks prepare Human3.6M motion data, make a fixed 135-clip training / 15-clip validation split from subjects S1, S5, S6, S7 and S8, and train a clean A0 diffusion baseline from random initialization. Subjects S9 and S11 are reserved for final testing. The notebooks also generate the modified diffusion-loss and discriminator source files for later stages.

- `cv-main-corrected.ipynb`: initial A0 training, up to 20 epochs per run.
- `cv-a0-120epochs.ipynb`: continuation run, up to 120 epochs or 10 hours, whichever comes first. Attach the previous A0 notebook output as a Kaggle Input to resume.

The official pretrained CoMusion checkpoint was trained on all 150 training clips, including the 15 used here for validation. Earlier short A2/A4 pilot metrics using that checkpoint are engineering smoke tests, **not valid model-selection results**. A0 and future variants need the same clean split and fresh initialization for a defensible comparison.

## Data and checkpoints

The Human3.6M data and large model checkpoints are not included here. Attach the prepared dataset as a Kaggle Input. Training checkpoints and logs are saved under `/kaggle/working/CoMusionGAN/artifacts` in the notebook output. Respect the dataset's access and redistribution terms.

The baseline project is [CoMusion](https://github.com/jsun57/CoMusion); retain its attribution and license when reusing its code.
