# Image Feature Extraction, Clustering, and Analysis  
**Complete All Phases - Project Finalized**  

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
**Algorithms Implemented:**  
| Algorithm          | Key Strengths                          | Hyperparameters             |  
|---------------------|---------------------------------------|-----------------------------|  
| **K-Means**         | Best Silhouette Score (`0.3574`)      | `k=4` (Elbow Method)        |  
| **DBSCAN**          | Noise detection (40.86% noise ratio)  | `eps=0.5`, `min_samples=3`  |  
| **Agglomerative**   | Highest F1-Score (`0.5951`)           | `n_clusters=6` (Dendrogram) |  
| **MeanShift**       | Automatic cluster detection           | `bandwidth=1.22`            |  

**Visualization**:  
- 2D PCA plots for cluster separation.  
- Heatmaps for feature-cluster relationships.  

---

### 4. **Evaluation**  
**Metrics:**  
| Algorithm          | Precision | Recall  | F1-Score | Silhouette |  
|---------------------|-----------|---------|----------|------------|  
| K-Means             | 0.4398    | 0.6086  | 0.5012   | **0.3574** |  
| DBSCAN              | 0.2925    | 0.4636  | 0.3334   | -          |  
| Agglomerative       | **0.5688**| **0.6475** | **0.5951** | 0.3204 |  
| MeanShift           | 0.5116    | 0.5525  | 0.4926   | 0.2146     |  

**Key Findings**:  
- **Agglomerative Clustering**: Best balance between precision and recall.  
- **K-Means**: Clear cluster boundaries (highest Silhouette Score).  

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



