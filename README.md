# 🏭 Supply Chain Vendor Performance Analytics

![Power BI](https://img.shields.io/badge/Power_BI-Dark_Mode-F2C811?style=for-the-badge&logo=powerbi)
![Python](https://img.shields.io/badge/Python-Data_Processing-3776AB?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Analytics-150458?style=for-the-badge&logo=pandas)

### **Overview**
This project helps supply chain managers optimize procurement by identifying underperforming vendors. It uses a **Python-based weighted scoring algorithm** to evaluate vendors on reliability, speed, and cost, and visualizes the results in an interactive **Power BI Dashboard**.

The system replaces manual Excel tracking with an automated pipeline that flags "At Risk" vendors instantly.

---

### **📊 The Dashboard (Power BI)**
*A dark-mode, glassmorphism-styled dashboard for executive monitoring.*

**Key Features:**
* **KPI Cards:** Tracks total active vendors and average fleet performance.
* **Top/Bottom Analysis:** instantly highlights the top 5 best and worst partners.
* **Searchable Slicer:** Allows detailed drill-down into specific vendor metrics.
* **UI/UX:** Custom "Dark Mode" aesthetic with semi-transparent glassmorphism cards.

---

### **🧠 The Logic: Weighted Scoring Model**
Instead of guessing which vendor is "best," I engineered a quantitative scoring model (0-100) based on three critical metrics.

#### **1. The Metrics**
| Metric | Weight | Description |
| :--- | :--- | :--- |
| **On-Time Delivery** | **50%** | (1 / Average Lead Time). Prioritizes speed. |
| **Quality/Reliability** | **30%** | Based on fulfillment rates and order consistency. |
| **Cost Competitiveness**| **20%** | (Global Avg Price / Vendor Price). Lower cost = Higher score. |

#### **2. The Algorithm (Python)**
The data was processed using Pandas. Raw metrics were **normalized** to a 0-1 scale to ensure fair comparison between large and small vendors.

$$Final Score = (OnTime \times 0.5) + (Quality \times 0.3) + (Cost \times 0.2)$$

---

### **🛠️ Tech Stack**
* **Data Processing:** Python (Pandas, NumPy)
* **Visualization:** Microsoft Power BI
* **Data Storage:** CSV / Local SQL
* **Environment:** Jupyter Notebook

---

### **📂 Project Structure**
```bash
├── data/
│   ├── raw_supply_chain_data.csv    # Original dataset
│   └── processed/
│       ├── vendor_scorecard.csv     # Final scores for Power BI
│       └── cleaned_purchases.csv    # Time-series data
├── notebooks/
│   └── vendor_analysis.ipynb        # Python logic & scoring algorithm
├── powerbi/
│   └── vendor_performance.pbix      # The Dashboard file
└── README.md