# Conda Setups for Data Science & AI (Apple Silicon)

This repository contains reproducible Conda environment configurations for **Data Science**, **AI** and **Machine Learning** projects.  
Each environment is purpose-built and optimized for **macOS ARM (M1/M2/M3)** using the `conda-forge` channel and the `libmamba` solver for fast, reliable and conflict-free installations.

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
# Configure conda (run once)
conda activate base
conda config --add channels conda-forge
conda config --set channel_priority strict
conda update -n base conda conda-libmamba-solver -y

# Create any environment (example: ds-core)
conda env create -f ds-core.yml
conda activate ds-core

# Register kernel for Jupyter / VS Code / IDE
python -m ipykernel install --user --name ds-core --display-name "Python (ds-core)"

# Check installed kernels
jupyter kernelspec list

# Export environment (to lock versions)
conda activate ds-core
conda env export --no-builds > environment.yml
conda deactivate

# Recreate environment elsewhere
conda env create -f environment.yml

```

🔎 Notes
- Always run setup commands from the base environment.
- If a kernel does not appear in Jupyter, re-run the ipykernel install command for that environment.
- Use conda-forge with strict channel priority for consistent ARM builds.
- Repeat the process for other environments (dl-tf.yml, dl-torch.yml, geo.yml, scraping.yml).

## 📁 Repository Structure

```css
conda-setups/
├── README.md
├── ds-core.yml
├── dl-tf.yml
├── dl-torch.yml
├── geo.yml
└── scraping.yml
```

### 💡 Why This Repository
- Ensures reproducibility across all Data Science and AI projects.
- Keeps dependencies clean, modular and purpose-specific.
- Enables others to recreate the exact same environments with a single command.
- Serves as a foundation for all professional and academic projects included in my portfolio.
  
### ⚖️ License
Distributed under the MIT License.
See LICENSE for details.

### Author:
CGD
