# Medical MRI Image Enhancement

A lightweight pipeline for **enhancing brain MRI scans** using a U‑Net‑based GAN and evolutionary hyperparameter optimization. The goal is to improve contrast and structural detail for better diagnostic utility.

---

## 📚 Background & Theory

Medical MRI scans often suffer from low contrast and noise, making it challenging to distinguish fine anatomical structures critical for diagnosis. Traditional contrast enhancement methods (e.g., histogram equalization) improve global brightness but can introduce artifacts or fail to preserve local details. 

**Generative Adversarial Networks (GANs)** solve this by framing enhancement as an adversarial game between two networks: a **generator** that learns to produce realistic, high-contrast images from low-contrast inputs, and a **discriminator** that learns to distinguish enhanced images from true high-quality images. We employ a **U‑Net** style generator with skip connections to preserve spatial information and a **PatchGAN** discriminator to focus on local texture realism.

To further refine model performance, we integrate an **Evolutionary Strategy (ES)** that automatically searches for optimal hyperparameters (such as filter counts, kernel sizes, and dropout rates) by evolving a population of candidate configurations based on their reconstruction fitness. This meta-learning approach reduces manual tuning and yields better convergence.

Finally, we apply **Contrast Limited Adaptive Histogram Equalization (CLAHE)** to the generator’s output, boosting local contrast while limiting noise amplification.

---

## 🔧 Prerequisites
- Python 3.7+
- TensorFlow 2.x
- OpenCV, NumPy, Matplotlib, tqdm

Install all requirements:
```bash
pip install -r requirements.txt
```

---

## 📥 Clone the Repository
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```


## 📊 Evaluation
- Quantitative metrics: **PSNR**, **SSIM** (scripts in `src/train.py` or notebooks).
- Visual comparisons available in `notebooks/FINAL_EC_ATML.ipynb`.

---

## 📝 License
This project is licensed under the **MIT License**.

