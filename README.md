# IT Salary Classification in Vietnam

## 🎯 **Project Overview**
This repository contains a comprehensive machine learning project focused on **classifying IT salary levels in Vietnam** using job posting data from multiple recruitment platforms. The project aims to predict salary ranges based on various features including skills, experience, location, company characteristics, and job requirements.

## 📊 **Data Sources & Scope**
The project analyzes job postings from **three major Vietnamese recruitment platforms**:
- **VietnamWorks** 
- **CareerViet** 
- **TopCV**

**Dataset Size**: 3,047 job postings with 14 features each  
**Data Collection Period**: End of April 2025  
**Language**: Mixed Vietnamese and English job descriptions  
**Data Quality**: High-quality job postings with comprehensive skill requirements and salary information

### **Dataset Details**
- **Total Records**: 3,047 job postings
- **Features**: 14 columns including company info, salary, skills, location, experience
- **Salary Range**: 1M - 100M VND (Vietnamese Dong)
- **Experience Range**: 0-16 years
- **Geographic Coverage**: 63 provinces/cities in Vietnam
- **Company Fields**: 25+ industry categories
- **Skills Extracted**: 277 technical skills across 6 categories
- **Missing Data**: <5% missing values after preprocessing
- **Data Freshness**: Collected end of April 2025, representing current market conditions

## 🏗️ **Project Structure**

### **Data Directory (`/data/`)**
- `job_en_with_skills.csv` - Main processed dataset with extracted skills
- `job_en.xlsx` - Original raw job posting data
- `skill.csv` - Skill taxonomy with 277 skills categorized into 6 groups

### **Preprocessing Directory (`/preprocess/`)**
- `1 extract_feature.ipynb` - Feature extraction and data preprocessing
- `2 visualization.ipynb` - Data visualization and exploratory analysis  
- `3 machine learning.ipynb` - Model training, evaluation, and classification
- `vietnamworks.ipynb` - VietnamWorks-specific data preprocessing
- `careerviet.ipynb` - CareerViet data preprocessing
- `company_fields.json` - Company field categorization mapping

### **Generated Visualizations (`/fig*.png`)**
- 7 visualization files showing data distributions, skill analysis, and model results

## 🔧 **Technical Implementation**

### **Data Processing Pipeline**
1. **Data Collection**: Scraped from 3 recruitment platforms
2. **Feature Extraction**: 
   - Skills extraction using regex pattern matching
   - Salary parsing (VND/USD conversion)
   - Experience level categorization
   - Company field standardization
3. **Data Augmentation**: Text augmentation for job descriptions
4. **Feature Engineering**: Target encoding, skill grouping, experience categorization

### **Skill Classification System**
The project uses a sophisticated skill taxonomy with **277 skills** organized into **6 categories**:
- **Languages** (68 skills): Java, Python, JavaScript, SQL, etc.
- **Libs & Frameworks** (62 skills): React, Spring, Django, etc.
- **OS & Infrastructure** (64 skills): AWS, Docker, Linux, etc.
- **Data Systems** (39 skills): MySQL, MongoDB, Big Data, etc.
- **Development Tools** (28 skills): Git, Jenkins, Maven, etc.
- **Process & Methods** (36 skills): Agile, Testing, Design, etc.

### **Machine Learning Approach**
- **Problem Type**: Multi-class classification (3 salary levels)
- **Salary Categories**: 
  - Low: 0-8.5M VND
  - Medium: 8.5M-17M VND  
  - High: 17M+ VND
- **Models Tested**: Logistic Regression, KNN, Random Forest, Decision Tree, XGBoost, Gradient Boosting
- **Best Performance**: Decision Tree with 87.16% accuracy

### **Key Features Used**
- **Experience**: Years of experience (0-16 years)
- **Skills**: Number and type of technical skills
- **Location**: Geographic distribution (Hanoi, Ho Chi Minh, etc.)
- **Company**: Field, scale, and characteristics
- **Position**: Job level and type
- **Platform**: Source recruitment platform

## 📈 **Key Findings & Insights**

### **Salary Distribution**
- **Average Salary**: 22.8M VND (~$900 USD)
- **Range**: 1M - 100M VND
- **Geographic Concentration**: Hanoi and Ho Chi Minh City dominate

### **Skill Analysis**
- **Most Demanded Skills**: Design (1,530 mentions), Data (768), Performance (593)
- **Skill Groups**: Process & Methods most common (2,160 mentions)
- **Technical Skills**: SQL, Java, Python, JavaScript most frequent

### **Experience Impact**
- **Fresher** (< 1 year): Lower salary range
- **Junior** (1-3 years): Mid-range salaries
- **Senior** (3+ years): Highest salary potential

### **Model Performance**
- **Best Model**: Decision Tree (87.16% accuracy)
- **Feature Importance**: Experience (28.9%), Company field (15.6%), Skills count (15.2%)
- **Ablation Study**: Experience removal causes largest performance drop

## 🛠️ **Technical Stack & Environment**

### **System Requirements**
- **Python Version**: 3.12
- **Operating System**: Windows 10/11 (tested on win32 10.0.26100)
- **Shell**: PowerShell v1.0

### **Core Libraries & Versions**
- **pandas**: Data manipulation and analysis
- **numpy**: Numerical computing
- **scikit-learn**: Machine learning algorithms
- **matplotlib**: Data visualization
- **seaborn**: Statistical data visualization
- **xgboost**: Gradient boosting framework
- **openpyxl**: Excel file processing
- **unidecode**: Text normalization
- **googletrans**: Text translation (4.0.0-rc1)
- **shap**: Model interpretability
- **kneed**: Elbow method for optimal clustering

### **Data Processing Tools**
- **Regex Pattern Matching**: Skill extraction and text processing
- **Text Preprocessing**: Vietnamese/English text normalization
- **Feature Engineering**: Target encoding, skill grouping, experience categorization
- **Data Augmentation**: Text augmentation for job descriptions

### **Machine Learning Techniques**
- **Classification**: Multi-class salary level prediction
- **Feature Engineering**: Advanced feature extraction and selection
- **Hyperparameter Tuning**: Model optimization
- **Model Interpretability**: SHAP values and feature importance analysis

## 🎯 **Business Applications**
This project provides valuable insights for:
- **Job Seekers**: Understanding salary expectations based on skills and experience
- **HR Professionals**: Market salary benchmarking and recruitment planning
- **Companies**: Competitive salary analysis and talent acquisition strategies
- **Researchers**: IT labor market analysis in Vietnam

## 🚀 **How to Run**

### **Prerequisites**
- Python 3.12 installed
- Jupyter Notebook or JupyterLab
- Windows 10/11 (recommended)

### **Installation**
1. Clone the repository:
```bash
git clone <repository-url>
cd IT_salary_in_Vietnam
```

2. Install required dependencies:
```bash
pip install numpy pandas scikit-learn matplotlib seaborn xgboost openpyxl unidecode googletrans==4.0.0-rc1 shap kneed
```

### **Execution**
Run the notebooks in the following order:
1. `preprocess/1 extract_feature.ipynb` → Preprocess data & extract features
2. `preprocess/2 visualization.ipynb` → Generate visualizations and statistical analysis
3. `preprocess/3 machine learning.ipynb` → Train and evaluate salary classification models

### **Data Access**
- **Raw Data**: `data/job_en.xlsx` (original dataset)
- **Processed Data**: `data/job_en_with_skills.csv` (with extracted skills)
- **Skill Taxonomy**: `data/skill.csv` (277 skills in 6 categories)

## 📊 **Output**
- **File 2 (`visualization.ipynb`)**: Generates visualizations showing data distribution and feature relationships
- **File 3 (`machine learning.ipynb`)**: Produces classification results, accuracy metrics, and model performance analysis
- **Generated Figures**: 7 PNG files with comprehensive data visualizations

## 📧 **Contact**
For dataset access or further assistance, please contact the author.

---

This repository represents a comprehensive analysis of Vietnam's IT job market, combining data science techniques with practical business insights to understand salary determinants in the technology sector.
