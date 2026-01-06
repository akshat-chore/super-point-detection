# Super-Point Detection

A focused research/demo repository containing a Jupyter Notebook that implements and demonstrates a self-supervised SuperPoint-style interest point detection pipeline with visualization and basic descriptor/matching workflows.

## Contents

- SuperPoint_Self_Supervised_Interest_Point_Detection.ipynb — Main Jupyter notebook (demo, experiments, visualizations)
- README.md — this file

## Overview

This repository provides an exploratory implementation of interest point detection inspired by SuperPoint. The notebook demonstrates data loading, model or algorithm steps, visualizations (keypoints, heatmaps, matches), and evaluation examples. It is intended to be run interactively in Jupyter or Colab.

## Requirements

Install common packages used by the notebook:

Using pip:
pip install jupyterlab notebook numpy matplotlib opencv-python scikit-image torch torchvision tqdm seaborn scipy

Using conda:
conda create -n superpoint python=3.9
conda activate superpoint
conda install -c conda-forge jupyterlab numpy matplotlib opencv scikit-image seaborn scipy
pip install torch torchvision tqdm

Install the appropriate PyTorch build for your CUDA version following https://pytorch.org if you plan to use GPU acceleration.

## How to run

1. Clone the repository:
   git clone https://github.com/akshat-chore/super-point-detection.git
   cd super-point-detection

2. Start Jupyter Notebook or JupyterLab and open the notebook:
   jupyter notebook SuperPoint_Self_Supervised_Interest_Point_Detection.ipynb
   or
   jupyter lab

3. Run the notebook cells sequentially to reproduce the pipeline and visual outputs.

### Run in Google Colab

Open the notebook in Colab:
https://colab.research.google.com/github/akshat-chore/super-point-detection/blob/main/SuperPoint_Self_Supervised_Interest_Point_Detection.ipynb

If packages are missing, install them in a setup cell at the top of the Colab notebook:
!pip install torch torchvision opencv-python matplotlib scikit-image tqdm

### Convert to script

To convert the notebook to a Python script:
jupyter nbconvert --to script SuperPoint_Self_Supervised_Interest_Point_Detection.ipynb

Adapt the generated script for automated or headless execution.

## Data and inputs

- The repository does not include datasets or pre-trained weights.
- Inspect the notebook to find where `data_path`, `image_paths`, or similar variables are set and point them to your local images or dataset directory.
- Common datasets for interest-point experiments: HPatches, Oxford/Paris image pairs, HPatches-like synthetic transformations, or custom imagery.

## Typical notebook outputs

- Visual overlays of detected keypoints on images
- Confidence / heatmap visualizations
- Descriptor extraction and matching visualizations
- Qualitative evaluation plots

## Troubleshooting

- If visualizations do not display, ensure the notebook kernel is running and use `%matplotlib inline` or the appropriate Jupyter display settings.
- If PyTorch raises device errors on machines without CUDA, set device to CPU (e.g., `device = torch.device("cpu")`).
- Resolve import issues by confirming packages are installed in the active environment.

## Notes

- No LICENSE file is included in this repository.
- Maintainer: akshat-chore — open issues on the repository for questions or requests.
