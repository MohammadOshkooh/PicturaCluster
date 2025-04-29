#### A University Project for Image Feature Extraction, Clustering, and Analysis
---

## 📌 Overview  
This project systematically processes images through **feature extraction**, **dimensionality reduction**, **clustering**, and **evaluation** to enable intelligent image categorization. Designed for educational and research purposes, it leverages advanced computer vision and machine learning techniques to analyze and cluster images based on visual patterns.  

---

## 🛠️ Project Phases  

### 1. **Feature Extraction**  
**Key Features Extracted:**  
- **Color Analysis**: HSV histograms (Hue, Saturation, Value).  
- **Sharpness**: Laplacian Variance to detect blurry vs. sharp images.  
- **Structural Complexity**: Edge Density using Canny edge detection.  
- **Statistical Measures**: Mean, variance, and entropy of grayscale intensity.  
- **Texture Analysis**:  
  - *Color Variance* (diversity of colors).  
  - *Roughness* (abrupt intensity changes).  
  - *Entropy* (randomness/complexity).  
  - *Homogeneity* (texture uniformity).  

**Libraries**: `OpenCV`, `Scikit-Image`, `NumPy`  

---

### 2. **Feature Selection**  
**Optimization Techniques:**  
- **PCA**: Applied to HSV histograms to reduce dimensionality while preserving 95% variance.  
- **Correlation Analysis**: Removed redundant features (threshold: `|r| > 0.85`).  
- **Silhouette Score**: Evaluated feature subsets to maximize cluster separation.  

**Final Features**:  
`HSV_PCA1`, `HSV_PCA2`, `HSV_PCA3` (color components), `Homogeneity` (texture uniformity).  

---

### 3. **Clustering**  

**Visualization**:  
- 2D PCA plots for cluster separation.  
- Heatmaps for feature-cluster relationships.  

---

### 4. **Evaluation**  


---

### 5. **Prediction Phase**  
- Predict cluster labels for new images using the trained K-Means model.  
- Display test images alongside **5 nearest neighbors** from their predicted clusters.  

---

## ⚙️ Installation  
```bash
pip install numpy opencv-python scikit-image seaborn pandas matplotlib scikit-learn
```

## 🚀 How to Run
Clone the repository:

bash
```
git clone https://github.com/your-username/image-clustering-project.git
```
Launch Jupyter Notebook:

bash
```
jupyter notebook
```
Open and run main.ipynb step-by-step.


## 📝 Notes

- Organize images in data/train/ and data/test/ folders.

- Adjust hyperparameters (e.g., k, eps) for custom datasets.

- Review inline comments in the notebook for detailed explanations.



