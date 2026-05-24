# Social Media Addiction: A Visual Analytics Approach

**CS661: Big Data Visual Analytics Project**  
*2024–2025 Semester III*

Social media addiction among students has emerged as a significant behavioral and academic issue. It not only affects academic performance but also disrupts sleeping habits and increases stress levels. Understanding these patterns through a visual interface is essential for awareness and corrective actions.

---

## Objectives
- **Build a dynamic visual interface** that highlights trends in student social media behavior.
- **Identify and segment addiction severity** across various demographics (gender, academic level, age).
- **Explore correlations** between high addiction scores and academic decline, sleep deprivation, and mental health.
- **Utilize clustering techniques** to group students into meaningful behavioral profiles.
- **Assist educational institutions, counselors, and students** in interpreting these patterns to foster healthier digital habits.

---

## ataset Description

- **Source:** The dataset used is titled ["Students Social Media Addiction"](https://www.kaggle.com/datasets/pratyushpuri/students-social-media-addiction) and is publicly available on Kaggle. It was created through a structured survey to analyze behavioral and psychological patterns among students.
- **Structure and Fields:** The dataset consists of ~1,000 entries with key attributes including:
  - **Demographics:** Gender, Age, Academic Level, Country
  - **Platform Preferences:** Most Used Platform, Device Used
  - **Usage Metrics:** Average Daily Usage (hours), Sleep Hours Per Night
  - **Addiction and Mental Health:** Addicted Score (numeric), Mental Health Score, Addiction Level (Low, Medium, High)
  - **Academic Indicators:** GPA, Affects Academic Performance (Yes/No)

---

## Data Processing

Before analysis, several preprocessing steps were executed:
1. **Missing Data Handling:** Dropped records missing essential fields (e.g., addiction scores, academic performance). Non-critical missing entries were filled with the mode or left as-is.
2. **Feature Engineering:** 
   - Created an *Addiction Level* field by binning the continuous *Addicted Score* into "Low," "Medium," and "High".
   - Transformed age into categorical *Age Groups* (16–18, 19–21, 22–24).
3. **Categorical Encoding:** Label encoded variables like Gender, Academic Level, and Platform Used for clustering and numerical comparison.
4. **Normalization:** Applied min-max scaling to features like Sleep Hours, Mental Health Score, and Daily Usage prior to dimensionality reduction (t-SNE).

---

## Tasks and Visual Analytics Goals
- **Examine demographic variation:** Understand how addiction severity differs across gender, academic level, and age.
- **Investigate academic impact:** Explore the correlation between addiction scores and reported academic decline.
- **Compare sleep patterns:** Identify if high addiction scores correlate with lower average sleep durations.
- **Analyze platform preference:** Determine which platforms are most associated with high addiction.
- **Identify behavioral clusters:** Segment students based on addiction, sleep, and device usage using t-SNE and KMeans.
- **Enable interactive filtering:** Support personalized data exploration through dashboard filters.

---

## 📁 Repository Structure

├── 46_Assignment1.zip                             # Assignment 1 solutions & approaches
├── group46_230806_240726_230689_Assignment2.zip   # Assignment 2 solutions & approaches
├── CS661_Project_Report_Group10.pdf               # Final Project Report (PDF)
├── app.py                                         # Dashboard main application file
├── README.md                                      # Project documentation
└── CS661_Final.zip                                # Core project production files
    ├── Students_Social_Media_Addiction.csv         # Raw source dataset from Kaggle
    ├── Processed_Students_Social_Media_Addict.csv  # Standardized and cleaned dataset
    ├── DataProcessingandVisualization.ipynb        # Data preparation & EDA notebook
    ├── app.py / app.ipynb                         # Dash frontend & visualization implementation
    ├── requirements.txt                           # Project dependencies
    ├── GroupX_proposal.pdf                        # Initial project proposal blueprint
    ├── CS661_Project_Report_Group10.pdf           # Project report copy
    └── Visualizations & Plots (PNGs):
        ├── Addiction Score by demographic.png
        ├── Addiction Score by Gender, Academic Level.png
        ├── Addiction Score by Most Used Platform.png
        ├── Addiction Score vs Academic Performance.png
        ├── Average Study Hours by Addiction Level.png
        └── Cluster Grouping of Students (t-SNE).png

---

## Dashboard Implementation

### Tech Stack
- **Python Dash:** Frontend interaction
- **Pandas & NumPy:** Data handling
- **Scikit-learn:** Clustering and preprocessing
- **Plotly:** Interactive visualizations

### Features
- Dynamic plots based on academic level, age, and gender filters.
- Interactive scatter, histogram, and bar charts with hover tooltips.
- 2D clustering projection for deeper insights.
- Responsive, modular layout with organized tabs.

---

## Design Justification

- **Histograms:** Ideal for visualizing the distribution of scores and detecting skewness/peaks across subgroups.
- **Box Plots:** Provides a compact summary of medians, quartiles, and outliers for multi-dimensional demographic comparisons.
- **Scatter Plots (with Regression):** Effectively identifies correlations (e.g., addiction vs. academic disruption) while displaying data spread.
- **Grouped Bar Charts:** Best suited for comparative visualizations like average sleep hours across categories.
- **t-SNE Cluster Plots:** Projects multi-dimensional behavioral data into a digestible 2D visual segmentation.

---

## Conclusion
This project successfully uncovers and visualizes social media addiction patterns among students. Key takeaways include:
- **Undergraduate males** show higher and more variable addiction scores.
- **Instagram and TikTok** are the platforms most correlated with high addiction levels.
- High addiction directly links to **lower sleep hours** and **negatively affected academic performance**.
- **Clustering analysis** proves highly valuable in grouping students into interpretable risk segments.

With rising concerns over digital wellness, this dashboard provides a practical, interactive tool for educators, researchers, and students to spark meaningful discussions and interventions.

---

## References
- **Dataset:** [Students Social Media Addiction (Kaggle)](https://www.kaggle.com/datasets/pratyushpuri/students-social-media-addiction)
- **Plotly Python Graphing Library:** [https://plotly.com/python/](https://plotly.com/python/)
- **Dash by Plotly:** [https://dash.plotly.com/](https://dash.plotly.com/)
- **t-SNE Methodology:** van der Maaten and Hinton, 2008
