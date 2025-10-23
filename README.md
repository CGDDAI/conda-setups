# Conda Setups for Data Science & AI (Apple Silicon)

This repository contains reproducible Conda environment configurations for Data Science, AI and Machine Learning projects.
Each environment is tailored for a specific purpose and optimized for **macOS ARM (M1/M2/M3)** using the `conda-forge` channel and the `libmamba` solver for fast, conflict-free installs.

---

## Available Environments

| Environment | Purpose | Key Libraries |
|--------------|----------|----------------|
| **ds-core** | Core Data Science & EDA | Pandas, NumPy, Scikit-learn, Matplotlib |
| **dl-tf** | Deep Learning (TensorFlow + Metal) | TensorFlow 2.16, Keras, TensorBoard |
| **dl-torch** | Deep Learning (PyTorch MPS) | PyTorch, TorchVision, Lightning |
| **geo** | Geospatial & Climate Analytics | GeoPandas, Rasterio, Cartopy, Xarray |
| **scraping** | Web Scraping & Automation | Requests, HTTPX, BeautifulSoup, Playwright |

---

## ⚙️ Quick Start

```bash
# Configure conda (once)
conda activate base
conda config --add channels conda-forge
conda config --set channel_priority strict
conda update -n base conda conda-libmamba-solver -y

# Create any environment
conda env create -f ds-core.yml
conda activate ds-core

# Register kernel for Jupyter
python -m ipykernel install --user --name ds-core --display-name "Python (ds-core)"
