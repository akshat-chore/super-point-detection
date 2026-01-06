# Super-Point Detection

A focused research/demo repository containing a Jupyter Notebook that implements and demonstrates self-supervised SuperPoint-style interest point detection and basic descriptor/matching workflows. The repository is organized around a single notebook which contains the data loading, model or algorithm demonstrations, visualization, and evaluation examples.

This README explains what is in the repository, how to run the notebook, required dependencies, and recommended next steps.

---

## Contents

- SuperPoint_Self_Supervised_Interest_Point_Detection.ipynb — Main Jupyter notebook (demo, experiments, visualizations)
- README.md — this file

---

## Overview

The notebook demonstrates a self-supervised approach for detecting interest points (keypoints) in images and optionally computing/visualizing descriptors and matches between images. It is intended as an exploratory/reproducible artifact you can run locally or in a hosted notebook environment to reproduce experiments and visual outputs.

Typical outputs you can expect from the notebook:
- Visualizations of detected keypoints over images
- Heatmaps or confidence maps for interest points
- Example descriptor extraction and matching visualizations
- Evaluation snippets (matching plots, qualitative comparisons)

Notes:
- The repository does not include datasets or pre-trained model weights. You will need to provide your own images/dataset or hook the notebook to a dataset location.

---

## Requirements

The notebook uses standard Python data-science and computer-vision libraries. Create a new environment and install these packages (example):

Using pip:

pip install jupyterlab notebook numpy matplotlib opencv-python scikit-image torch torchvision tqdm seaborn scipy

Using conda:

conda create -n superpoint python=3.9
conda activate superpoint
conda install -c conda-forge jupyterlab numpy matplotlib opencv scikit-image seaborn scipy
pip install torch torchvision tqdm

Adjust the torch installation for your CUDA version by following instructions at https://pytorch.org.

If you plan to run heavy model training or GPU-accelerated inference, make sure you have compatible CUDA drivers and install a CUDA-enabled PyTorch build.

---

## How to run

1. Clone the repository:
   git clone https://github.com/akshat-chore/super-point-detection.git
   cd super-point-detection

2. Start Jupyter (Notebook or Lab):
   jupyter notebook SuperPoint_Self_Supervised_Interest_Point_Detection.ipynb
   or
   jupyter lab

3. Open and run notebook cells sequentially. The notebook contains explanatory text cells and code cells—run them in order to reproduce the pipeline and visual outputs.

Alternative: run in Google Colab
- Upload the notebook to Colab or open it from GitHub using Colab:
  https://colab.research.google.com/github/akshat-chore/super-point-detection/blob/main/SuperPoint_Self_Supervised_Interest_Point_Detection.ipynb
- Install missing packages in the first Colab cell (e.g., pip install torch torchvision opencv-python).

Convert to script (for automation)
- You can convert the notebook to a Python script:
  jupyter nbconvert --to script SuperPoint_Self_Supervised_Interest_Point_Detection.ipynb
- Then adapt the generated script for CLI usage or batch processing.

---

## Data / Inputs

- The notebook expects image inputs. There is no dataset bundled in the repo.
- Inspect the notebook to find the cell(s) where `data_path`, `image_paths`, or similar variables are defined and point them to your image directory.
- Recommended datasets for interest-point / matching experiments:
  - HPatches, Oxford/Paris image pairs, or your own aerial / street imagery for land-use scenarios.

---

## Tips & troubleshooting

- If visualizations do not appear, ensure you are running the notebook in a browser and that matplotlib inline or equivalent is enabled.
- If PyTorch is used and CUDA is not available, set the device to CPU in the notebook (search for `device = torch.device(...)`).
- For large notebooks/long-running cells, run cells individually and save checkpoints frequently.
- If you get import errors, double-check that the installed package versions are compatible (especially OpenCV and PyTorch).

---

## Recommended improvements (if you want to extend this repo)

- Add a small requirements.txt or environment.yml for reproducibility.
- Provide a short example dataset in a `data/example/` folder (few images) so new users can run the notebook end-to-end immediately.
- Add a lightweight script wrapper (e.g., run_demo.py) that executes the notebook pipeline headlessly for automation.
- Add a CONTRIBUTING.md and LICENSE file if you intend to publish or accept contributions.

---

## License and contact

- There is no license file in the repository. If you plan to publish or share this project, consider adding an explicit license (for example, MIT).
- Maintainer: akshat-chore — open issues on the repository for questions or requests.
