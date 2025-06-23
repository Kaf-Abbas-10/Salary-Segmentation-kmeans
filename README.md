
---

## 📌 Task Objective

The goal is to cluster individuals from a salary dataset into distinct groups based on various features such as:

- Age
- Education
- Work Type
- Gender
- Site Spending
- Site Time
- Recommendation Impression
- Salary

---

## 🧠 Logic and Working

### 🔹 Part 1: K-Means From Scratch

#### 📦 Libraries Used
- `NumPy` for numerical operations
- `pandas` for data handling
- `LabelEncoder` and `StandardScaler` from `sklearn.preprocessing` for preprocessing only

#### 🧹 Preprocessing Steps
1. **Label Encoding** of categorical features: `Education`, `WorkType`, `Gender`
2. **Feature Scaling** using `StandardScaler` for numeric stability
3. Optionally drop or modify features if required (this is marked as TODO in the code)

#### 🧮 K-Means Algorithm
The custom K-Means implementation follows these steps:
1. Randomly initialize `k` cluster centroids.
2. **E-step:** Assign each data point to the nearest centroid based on Euclidean distance.
3. **M-step:** Recalculate centroids as the mean of points assigned to each cluster.
4. Repeat steps 2-3 until centroids converge or max iterations reached.

#### ✅ Output
- A new column `Cluster` is added to the DataFrame indicating cluster assignment.

---

### 🔹 Part 2: Using `scikit-learn`

To validate the custom implementation, the same dataset is processed and clustered using `sklearn.cluster.KMeans`.

#### Code Flow
1. Load and preprocess dataset as in Part 1
2. Use `KMeans(n_clusters=k, max_iter=200)` from `sklearn`
3. Fit the model and predict clusters
4. Compare the output with Part 1

---

## 📊 Results

The notebook outputs the original dataset with an added `Cluster` column, showing which cluster each record belongs to based on the features.

---

## 🚀 How to Run

1. Ensure you have the required packages:
   ```bash
   pip install numpy pandas scikit-learn openpyxl
