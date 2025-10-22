# Week 03 — CNN Cancer Detection (Kaggle Mini‑Project)

Convolutional neural networks for histopathologic cancer detection on the Kaggle PCAM dataset. The notebook builds a fast image cache, creates stratified train/val splits, trains several lightweight CNN variants (including a DepthCNN and TinyResNet‑style blocks), profiles per‑batch timings, and tracks AUC/loss across sweeps (architecture, LR, weight decay, optimizer, depth).

## Contents
- Notebook: `CNN Cancer Detection Kaggle Mini-Project.ipynb`
- Plots: saved as `*.png` (AUC/loss curves, sweep summaries)
- Checkpoints: saved to `checkpoints/*.pth` (ignored by git)

## Data
- Option A: place the Kaggle dataset under this folder as `histopathologic-cancer-detection/` containing `train/`, `test/`, and `train_labels.csv`.
- Option B: set an environment variable to the dataset root (recommended to keep the repo clean):
  - macOS/Linux: `export PCAM_DIR=/path/to/histopathologic-cancer-detection`
  - Windows (PowerShell): `$env:PCAM_DIR = "C:\\path\\to\\histopathologic-cancer-detection"`
- The notebook will discover the dataset via `PCAM_DIR` or a local `histopathologic-cancer-detection/` directory.

## Environment
- Python 3.9–3.11 recommended
- Required packages: `torch`, `torchvision`, `numpy`, `pandas`, `scikit-learn`, `pillow`, `matplotlib`, `tqdm`, `torchinfo`
- Quick install:
  - `pip install torch torchvision numpy pandas scikit-learn pillow matplotlib tqdm torchinfo`

## Quick Start
1) Set `PCAM_DIR` or place the dataset under this folder (see Data section).
2) Launch Jupyter and open the notebook:
   - `jupyter lab` or `jupyter notebook`
3) Run cells in order:
   - Dataset discovery (prints a few file checks)
   - Build image cache (creates `cache_64/` with resized `.npy` tiles)
   - Train/val split and DataLoaders
   - Train either the DepthCNN section or the Architecture Sweep section
4) Inspect outputs:
   - Plots `*.png` at repo root
   - Best weights in `checkpoints/`

## Reproduce Best Model (DepthCNN example)
1) Ensure cache exists (run the cache cell using `IMG_SIZE = 64`).
2) Create DataLoaders and confirm sizes are printed.
3) Run the section titled “Train DepthCNN (d=7)” to train for ~10 epochs; the script saves `checkpoints/DepthCNN_d7_best.pth` when validation AUC improves.
4) Use the saved weights for inference or for generating submission probabilities.

## Notes
- Apple Silicon: MPS is detected automatically; the notebook uses `num_workers=0` and disables `pin_memory` when on MPS.
- Augmentations/normalization hooks are documented in the notebook’s transform cells if you wish to extend training.
- Large artifacts (raw dataset, cache, checkpoints, submissions) are ignored by `.gitignore` to keep the repo light.

