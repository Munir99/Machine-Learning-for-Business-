# Machine-Learning-for-Business-

# 🛢️ OilyGiant Oil Well Location Optimization

## 📍 Project Description

You're working as an analyst for **OilyGiant**, a mining company planning to open a new oil well. Your task is to determine the most profitable region for development using machine learning and statistical analysis.

You'll:

- Analyze oil well characteristics and reserve volumes
- Build a linear regression model to predict reserves
- Identify the top-performing wells in each region
- Evaluate potential profits and risks using bootstrapping

---

## 🗺️ Project Objective

Determine which of the **three regions** is the most promising for developing oil wells based on:

- Model-predicted oil reserves
- Expected profit from top 200 wells out of 500
- Risk of loss (using statistical sampling)

---

## 📦 Datasets

Available in CSV format:

- `geo_data_0.csv`
- `geo_data_1.csv`
- `geo_data_2.csv`

Each file contains:

| Column | Description |
|--------|-------------|
| `id`   | Unique oil well identifier |
| `f0`, `f1`, `f2` | Geological features (meaning unknown, but significant) |
| `product` | Volume of reserves (in thousand barrels) |

---

## ⚙️ Project Workflow

### Step 1: Data Preparation
- Load and inspect the datasets
- Check for missing values and data types
- Understand feature distributions
- Document key observations

---

### Step 2: Train and Test Linear Regression Models
For **each region**:

2.1. Split data into **training (75%)** and **validation (25%)**  
2.2. Train a linear regression model  
2.3. Make predictions on the validation set  
2.4. Calculate and print:
- Average predicted volume
- RMSE of the model

2.5. Analyze model performance

---

### Step 3: Profit Calculation Prep

3.1. Define key constants:
- Budget: **$100 million**
- Revenue per 1000 barrels: **$4,500**
- Wells to develop: **200**
- Total wells studied: **500**

3.2. Calculate **break-even point** for volume needed to avoid loss  
3.3. Compare this with **average reserves** across regions

---

### Step 4: Profit Estimation Function

4.1. Select the **top 200 predicted wells** out of 500  
4.2. Calculate total **target (actual)** reserves  
4.3. Estimate **expected profit**:
- Multiply reserves by revenue rate
- Subtract development costs

4.4. Summarize findings and **recommend** the region with highest return

---

### Step 5: Risk & Confidence Estimation

Use **bootstrapping (1000 iterations)** for each region:

5.1. Simulate profits by randomly sampling 500 wells  
5.2. For each sample:
- Select top 200
- Calculate actual total reserves
- Estimate profit

5.3. Record:
- **Average profit**
- **95% confidence interval**
- **Loss probability** (profit < 0), expressed as a **percentage**

5.4. Final Recommendation:
- Keep only regions with **<2.5% risk**
- From those, pick region with **highest average profit**

---

## 📌 Constraints & Assumptions

- Use **Linear Regression** only
- Only **200 out of 500** wells are developed
- Budget for 200 wells = **$100 million**
- Revenue per thousand barrels = **$4,500**
- Choose region with **risk < 2.5%** and **maximum expected profit**
- Data is synthetic; geological and contractual details are fictional

---

## 🧰 Tools & Libraries

- Python 3.x
- Pandas, NumPy
- Scikit-learn
- Matplotlib / Seaborn
- SciPy (for bootstrap confidence intervals)

---

## 🧠 Key Deliverables

- Model RMSE and average predicted reserves
- Profit calculation function
- Bootstrap risk analysis
- Final recommendation based on expected return and risk tolerance

