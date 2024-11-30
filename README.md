# Mapping-Learner-Career-Archetypes
**Scaler Synergy: Mapping Learner Career Archetypes**   This project focuses on clustering Scaler learners based on their job profiles, companies, and key attributes to identify patterns in successful career trajectories. The insights aim to enhance personalized learning paths and spotlight top roles and companies for Scaler graduates.

## **Project Overview**  
Scaler is an online tech-versity offering intensive courses in Computer Science and Data Science. This project focuses on analyzing the Scaler learner database to uncover patterns in job profiles, companies, and other features. Using clustering techniques, the goal is to segment learners into meaningful groups to enhance personalized learning, mentorship, and job placement support.

---

## **Key Objectives**  
1. **Data Analysis**: Explore and preprocess the dataset to uncover patterns and trends.
2. **Feature Engineering**: Create new features such as Years of Experience and CTC-based flags for in-depth analysis.
3. **Manual Clustering**: Segment learners based on company, job position, and years of experience.
4. **Unsupervised Learning**: Perform clustering using K-means and Hierarchical clustering techniques.
5. **Insights & Recommendations**: Provide actionable insights to improve Scaler’s business strategies.

---

## **Steps to Execute**

### **1. Data Exploration**
- Load the dataset and inspect its structure.
- Check for unique emails and their frequency.
- Record observations and inferences at every step.

### **2. Data Cleaning**
- Handle missing values using **KNN/Mean Imputation**.
- Remove special characters from text using **Regex**:
  ```python
  import re
  mystring = '\tAirtel X Labs'
  cleaned_string = re.sub('[^A-Za-z0-9 ]+', '', mystring)
  ```
- Detect and remove duplicates.

### **3. Feature Engineering**
- Create a **‘Years of Experience’** column by subtracting `orgyear` from the current year.
- Generate CTC summaries (mean, median, max, min, count) based on:
  - Company  
  - Job Position  
  - Years of Experience  

- Add CTC-based flags:  
  - **Designation Flag**: Compare learner CTC to the average CTC in their department for the same years of experience (`1, 2, 3`).  
  - **Class Flag**: Perform analysis at the company-job position level (`1, 2, 3`).  
  - **Tier Flag**: Perform analysis at the company level (`1, 2, 3`).  

### **4. Manual Clustering**
Answer the following questions:
- **Top/Bottom Employees**:
  - Top 10 Tier 1 (earning more than most employees in their company).
  - Top/Bottom 10 Data Science employees per company (Class 1/Class 3).
  - Bottom 10 Tier 3 (earning less than most employees in their company).
- **Top Performers in Departments**:
  - Top 10 employees in each department with 5/6/7 years of experience earning more than peers.
- **Top Companies and Positions**:
  - Top 10 companies based on CTC.
  - Top 2 positions in every company based on CTC.

### **5. Data Preparation for Clustering**
- Perform **Label Encoding** or **One-Hot Encoding** for categorical variables.
- Standardize the dataset for clustering.

### **6. Unsupervised Clustering**
- Check clustering tendency.
- Use the **Elbow Method** to determine the optimal number of clusters.
- Apply:
  - **K-means Clustering**
  - **Hierarchical Clustering** (sample dataset if process time is excessive).

### **7. Insights & Recommendations**
- Analyze clusters and draw insights.
- Provide actionable recommendations to enhance Scaler’s business strategies, such as:  
  - Customizing learning paths.  
  - Targeted mentorship programs.  
  - Focused placement assistance.

---

## **Technologies Used**
- **Python**: For data processing, EDA, feature engineering, and clustering.  
- **Libraries**: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `plotly`.  

---

## **Deliverables**
1. **Cleaned Dataset**: Processed and ready for analysis.  
2. **Clustering Analysis**: Models and evaluations.  
3. **Insights & Recommendations**: Actionable points to improve learner satisfaction and retention.  

---

## **How to Run the Project**
1. Install required Python libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
2. Load the dataset and follow the steps in the notebook.
3. Execute EDA, feature engineering, and clustering as outlined.
4. Analyze results and document insights.
