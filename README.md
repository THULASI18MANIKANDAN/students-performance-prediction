Student Performance Regression Analysis using Deep Learning (EDA Project)

Overview
This project analyzes and predicts student academic performance using the **UCI Student Performance Dataset**.  
The goal is to explore how demographic, social, and academic factors influence students’ **final grades (G3)** through **Exploratory Data Analysis (EDA)** and a **Deep Learning Regression model**.

The study focuses on:
- Understanding key factors affecting academic performance.
- Performing detailed data preprocessing and visualization.
- Building and evaluating a **Multi-Layer Perceptron (MLP)** regression model.


Dataset Description
**Source:** [UCI Machine Learning Repository – Student Performance Data Set](https://archive.ics.uci.edu/dataset/320/student+performance)

**Files:**
- `student-mat.csv` — Mathematics performance data  
- `student-por.csv` — Portuguese language performance data

**Attributes (Total ~33):**
- **Demographic:** age, gender, family size, address type  
- **Social:** parental education, school support, family relations  
- **Academic:** study time, failures, absences, previous grades (G1, G2)  
- **Target:** `G3` (final grade, range 0–20)

---

 Project Workflow

 **1️⃣ Data Understanding & Cleaning**
- Checked for missing values, duplicates, and outliers  
- Encoded categorical features using **OneHotEncoder**  
- Normalized numerical features using **StandardScaler**

**2️⃣ Exploratory Data Analysis (EDA)**
- **Visualizations created:**
  - Histogram of Final Grade (`G3`)
  - Correlation Heatmap
  - Boxplot by Gender
  - Scatter Plot (G1 vs G3)
  - Bar Chart (Students per School)
- **Insights:**
  - `G1` and `G2` strongly correlate with `G3`
  - Study time and absences have measurable effects on performance
  - Gender differences are minimal, but attendance impacts scores

### **3️⃣ Model Building (Deep Learning Regression)**
- Model Type: **Multi-Layer Perceptron (MLP)**
- Framework: **TensorFlow / Keras**
- Input: Encoded and scaled features  
- Output: Continuous target `G3`

**Model Architecture**
| Layer | Units | Activation | Dropout |
|--------|--------|-------------|----------|
| Dense | 64 | ReLU | - |
| Dense | 32 | ReLU | 0.1 |
| Dense | 1 | Linear | - |

**Training Parameters:**
- Optimizer: Adam (`lr = 0.001`)  
- Loss: Mean Squared Error (MSE)  
- Metrics: Mean Absolute Error (MAE)  
- Epochs: 80 | Batch Size: 32 | Validation Split: 15%

---

📊 Model Evaluation

| Metric | Value |
|---------|--------|
| RMSE | 1.87 |
| MAE | 1.32 |
| R² Score | 0.91 |

 **Result Visualizations**
- Loss vs Epoch (Training & Validation)
- MAE vs Epoch
- Predicted vs Actual Scatter Plot
- Residual Distribution
- Residuals vs Actual Target

**Interpretation:**
The model achieved strong predictive accuracy (R² ≈ 0.91), indicating excellent generalization.  
Residuals are normally distributed, confirming unbiased predictions.

---

Key Insights
- **Strong Predictors:** Previous grades (G1, G2), study time, and absences.  
- **Correlations:** Positive relationships between earlier grades and final performance.  
- **Generalization:** Deep learning regression performed well with minimal overfitting.

---

 Technologies Used
| Category | Tools / Libraries |
|-----------|------------------|
| Programming | Python 3.x |
| Data Analysis | Pandas, NumPy |
| Visualization | Matplotlib |
| ML / DL | Scikit-learn, TensorFlow, Keras |
| Environment | Jupyter Notebook / Google Colab |
| Version Control | Git & GitHub |

 How to Run

**Clone the Repository**
```bash
git clone https://github.com/<your-username>/Student-Performance-Regression-EDA.git
cd Student-Performance-Regression-EDA
