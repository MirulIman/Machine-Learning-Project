# **Random Forest Credit Default Prediction**  

## 📌 **Project Overview**  
This project builds a **Random Forest model** to predict **credit card default** based on demographic and financial data. The dataset consists of **30,000 credit card customers** and includes attributes such as **age, credit limit, past payment behavior, and bill amounts.**  

We perform:  
✅ **Data preprocessing & feature selection**  
✅ **Baseline model evaluation**  
✅ **Hyperparameter tuning** using `GridSearchCV`  
✅ **Performance evaluation with confusion matrix & classification metrics**  

---

## 📂 **Project Structure**  
```
├── data/                        # Dataset (UCI Credit Card Default Dataset)
│   ├── UCI_Credit_Card.csv
│
├── notebooks/                    # Jupyter Notebook
│   ├── Random_Forest_Credit_Default_Prediction.ipynb
│
├── src/                          # Source Code (if applicable)
│   ├── model.py                  # Model training script
│   ├── preprocess.py              # Data preprocessing script
│
├── results/                      # Model results
│   ├── confusion_matrix.png
│   ├── classification_report.txt
│
├── README.md                     # Project documentation (this file)
├── requirements.txt               # Python dependencies
```

---

## 🛠️ **Setup & Installation**  

### **1️⃣ Clone the Repository**  
```bash
git clone https://github.com/your-username/credit-default-prediction.git
cd credit-default-prediction
```

### **2️⃣ Create a Virtual Environment (Optional but Recommended)**
```bash
python -m venv env
source env/bin/activate  # For MacOS/Linux
env\Scripts\activate     # For Windows
```

### **3️⃣ Install Dependencies**  
```bash
pip install -r requirements.txt
```

---

## 📊 **Dataset**  
The dataset used in this project is the **UCI Credit Card Default Dataset**, available [here](https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients).  

- **Rows:** 30,000 customers  
- **Columns:** 25 features (Demographic & Credit History)  
- **Target Variable:** `default.payment.next.month`  
  - **0** → No Default  
  - **1** → Default  

### **Key Features**  
| Feature Name   | Description |
|---------------|------------|
| `LIMIT_BAL`   | Credit limit (in NT dollars) |
| `AGE`         | Customer's age |
| `PAY_0 - PAY_6` | Past payment status (delay in months) |
| `BILL_AMT1 - BILL_AMT6` | Bill statement amount for last 6 months |
| `PAY_AMT1 - PAY_AMT6` | Amount paid in the last 6 months |

---

## 📈 **Model Development**  

### **Baseline Model**  
We first train a **Random Forest model with default parameters**, achieving **82% accuracy**, but recall for defaulters is low.  

### **Hyperparameter Tuning**  
We optimize parameters such as:  
✔ `max_depth` (controls tree depth)  
✔ `n_estimators` (number of trees)  
✔ `max_features` (features considered per split)  
✔ `min_samples_split` (minimum samples to split a node)  
✔ `min_samples_leaf` (minimum samples per leaf)  

### **Final Model Performance**  
| Metric      | Class 0 (No Default) | Class 1 (Default) |
|------------|----------------------|-------------------|
| **Precision** | 0.84 | 0.69 |
| **Recall** | 0.96 | 0.35 |
| **F1-score** | 0.90 | 0.47 |
| **Overall Accuracy** | **82.6%** |

---

## 📉 **Key Insights**  

🔴 **Issue:**  
- The model has **high false negatives**, meaning it **misses many defaulters**, which is risky for banks.  

✅ **Solutions:**  
1️⃣ Apply **SMOTE (Synthetic Minority Oversampling Technique)** to balance classes.  
2️⃣ Try **XGBoost or Logistic Regression** with **class weighting**.  
3️⃣ Use **ROC-AUC & Precision-Recall curves** instead of relying only on accuracy.  

---

## 🚀 **How to Run the Code**  

### **1️⃣ Open the Jupyter Notebook**  
```bash
jupyter notebook
```
Run the `Random_Forest_Credit_Default_Prediction.ipynb` notebook step by step.

### **2️⃣ Train & Test Model via Script**  
If you prefer running the model as a script:
```bash
python src/model.py
```

---

## 📌 **Next Steps**  
🔹 Improve recall for default cases using class-balancing techniques.  
🔹 Test with **Gradient Boosting, XGBoost, and Logistic Regression**.  
🔹 Deploy the model as an **API using Flask or FastAPI**.  
🔹 Visualize decision-making with **SHAP values**.  

---

## 🤝 **Contributing**  
Contributions are welcome! If you'd like to contribute:  
1. **Fork** the repo  
2. Create a **feature branch** (`git checkout -b feature-name`)  
3. **Commit changes** (`git commit -m "Add feature XYZ"`)  
4. **Push** to GitHub (`git push origin feature-name`)  
5. Open a **Pull Request** 🎉  

---

## 📜 **License**  
This project is open-source and available under the **MIT License**.

---

Would you like me to generate a **requirements.txt** file for your dependencies as well? 😊
