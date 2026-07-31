# Urban Change Detection with Sentinel-2: A Two-Step Machine Learning Framework
This repository contains the complete code for the paper:
> "Evaluating the Impact of Super-Resolution on Urban Change Detection: A Two-Step Machine Learning Framework Using Sentinel-2, LightGBM, and XGBoost"
The project implements a two-step framework to evaluate whether super-resolution techniques (Real-ESRGAN and EDSR) can improve urban change detection using Sentinel-2 imagery.
---
## 🧠 Key Findings
- **LightGBM outperforms XGBoost** for urban change detection (F1 = 0.84 vs 0.56)
- **Super-resolution degrades boundary accuracy** (Boundary IoU drops from 0.43 to 0.05)
- **Non-SR approach with original Sentinel-2 imagery provides the most reliable results**
---

## 📁 Project Structure

```bash
├── Step_one.ipynb         # Step 1: Non-SR change detection (LightGBM, XGBoost, generalization tests)
├── Step_two.ipynb         # Step 2: SR-based change detection (Real-ESRGAN, EDSR, metrics comparison)
├── requirements.txt       # All dependencies
└── README.md              # This file
---

## 🔧 Requirements

Install all dependencies with:

```bash
pip install -r requirements.txt
Main libraries used:
numpy, pandas
opencv-python, rasterio
scikit-learn, xgboost, lightgbm
imbalanced-learn (SMOTE)
mahotas (Haralick texture features)
matplotlib, scipy, scikit-image
🚀 How to Run
Step 1: Non-SR Change Detection
Open and run Step_one.ipynb in Jupyter Notebook or Google Colab.
This notebook includes:
Feature extraction (spectral, texture, temporal)
Model training (LightGBM and XGBoost)
Generalization tests on Mumbai and Beirut
Step 2: Super-Resolution Change Detection
Open and run Step_two.ipynb in Jupyter Notebook or Google Colab.
This notebook includes:
Non-SR RGB baseline
Real-ESRGAN and EDSR super-resolution
Model training and evaluation
Boundary IoU and Hausdorff distance metrics
📊 Results Summary
Step 1: Non-SR Change Detection
City	Model	F1-Score	Kappa
Abu Dhabi (Train)	LightGBM	0.84	0.83
Mumbai (Test)	LightGBM	0.90	0.88
Beirut (Test)	LightGBM	0.85	0.82
Step 2: Super-Resolution Comparison
Model	SR Method	F1-Score	Boundary IoU
LightGBM	Non-SR	0.84	0.43
LightGBM	Real-ESRGAN	0.78	0.055
LightGBM	EDSR	0.75	0.05
XGBoost	Real-ESRGAN	0.56	0.032
## 📁 Outputs

Key output figures are available in the `outputs/` folder:

- `Figure_10_NonSR_Results.png` — Change detection results for Non-SR approach
- `Figure_11_RealESRGAN_Results.png` — Change detection results for Real-ESRGAN
- `Figure_12_EDSR_Results.png` — Change detection results for EDSR
- `Figure_13_FeatureImportance_RealESRGAN.png` — Top features for LightGBM with Real-ESRGAN
- `Figure_14_FeatureImportance_EDSR.png` — Top features for LightGBM with EDSR
- `Figure_15_PR_Curve.png` — Precision-Recall curve for threshold optimization
📄 Citation
If you use this code, please cite the accompanying paper once published.
For now, please refer to this repository and the author's GitHub page.
👤 Author
**Mahyar Tahmasebipour**  
BSc Student in Geomatics Engineering  
K.N. Toosi University of Technology, Tehran, Iran  
[GitHub](https://github.com/mahyartahmasebipour) • [Email](m.tahmasebi2@email.kntu.ac.ir)
**Elahe Khesali** (Supervisor)  
Department of Remote Sensing, Faculty of Geodesy and Geomatics Engineering  
K.N. Toosi University of Technology, Tehran, Iran  
[Email](mailto:elahe.khesali@kntu.ac.ir)
**Correspondence:** elahe.khesali@kntu.ac.ir
MIT License
Copyright (c) 2025 Mahyar Tahmasebipour
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
