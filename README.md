# 🛒 BigMart Sales Prediction

This project builds a machine learning model to predict Item Outlet Sales using the BigMart dataset stored in a MySQL database. It demonstrates data preprocessing, feature engineering, model building, evaluation, and saving the best model for deployment.

# 📌 Features

---

* Connects to MySQL Database to fetch data from multiple tables (item_info, outlet_info, sales_info).

* Performs data cleaning and feature engineering:

   * Handling duplicates & missing values.

   * Normalizing categorical variables.

   * Capping outliers in Item_Visibility.

   * Creating new feature: Outlet_Age.

* Trains and evaluates multiple models:

   * Gradient Boosting Regressor

   * Random Forest Regressor

   * Linear Regression

* Selects the best-performing model using R² Score.

* Saves the trained model as a pickle file (.pkl) for future use.


# 🛠️ Tech Stack

---

* Programming Language: Python 3.x

* Database: MySQL

* Libraries:

   * numpy, pandas, matplotlib, seaborn

   * pymysql (for DB connection)

   * scikit-learn (ML models, pipelines, preprocessing, evaluation)

   * pickle (for model persistence)
 
# 📂 Project Structure

---
 
BigMart-Sales-Prediction/

│

├── app.py / notebook.ipynb             # Main implementation file

├── requirements.txt                    # Dependencies

├── bigmart_best_model.pkl              # Saved best ML model

├── Bigmart_prediction_model_demo.webm  # Demo

└── README.md                           # Project overview 

# ⚙️ Setup & Installation

---

**1. Clone the Repository**
```
git clone https://github.com/your-username/bigmart-sales-prediction.git
cd bigmart-sales-prediction
```

**2. Install Dependencies**
```
pip install -r requirements.txt

```

**3. Database Setup**

* Create a MySQL database named BigMart.

* Import or create the following tables:

  * item_info

  * outlet_info

  * sales_info

**4. Update Database Credentials in the code:**

```
connection = pymysql.connect(
    host='localhost',
    user='root',
    password='your_password',
    database='BigMart'
)

```

# 🚀 Running the Project

---

```
python app.py

```

# 📊 Model Training & Evaluation

---

* Splits data into training (80%) and testing (20%).

* Evaluates each model using R² Score.

* Prints the performance of:

  * Gradient Boosting

  * Random Forest

  * Linear Regression

* Selects the best-performing model and saves it as:

```
bigmart_best_model.pkl
```

# 💾 Saving & Loading Model

---

The best model is saved along with the scikit-learn version:

```
import pickle, sklearn

with open('bigmart_best_model.pkl', 'wb') as f:
    pickle.dump((best_pipeline, sklearn.__version__), f)

```

To load it back:

```
with open('bigmart_best_model.pkl', 'rb') as f:
    model, sklearn_version = pickle.load(f)
```



