# Data Cleaning Project: Layoffs Dataset (2022)

## 📋 Project Overview
This project focuses on cleaning and preparing a real-world layoffs dataset from 2022 for analysis. The dataset contains information about companies, industries, locations, layoff statistics, funding, and other relevant business data.

## 🎯 Objectives
- Identify and remove duplicate records
- Standardize data formats and fix inconsistencies
- Handle null values appropriately
- Remove unnecessary columns and rows
- Create a clean, analysis-ready dataset

## 🛠️ Tools & Technologies
- **SQL** (MySQL)
- **Data Cleaning Techniques**
- **Kaggle Dataset Source**

## 📊 Dataset Information
- **Source**: [Kaggle Layoffs 2022 Dataset](https://www.kaggle.com/datasets/swaptr/layoffs-2022)
- **Original Table**: `world_layoffs.layoffs`
- **Staging Table**: `world_layoffs.layoffs_staging2`

## 🔧 Data Cleaning Steps

### 1. Data Duplication Handling
- Created staging table for safe data manipulation
- Identified duplicates using `ROW_NUMBER()` with `PARTITION BY` on all columns
- Removed exact duplicate records while preserving unique entries

### 2. Data Standardization
- **Industry Column**: 
  - Converted empty strings to NULL
  - Populated NULL values using company-matched records
  - Standardized variations (e.g., "Crypto Currency" → "Crypto")
  
- **Country Column**:
  - Removed trailing periods for consistency
  
- **Date Column**:
  - Converted from text to proper DATE format using `STR_TO_DATE()`
  - Updated column data type for better query performance

### 3. Null Value Management
- Analyzed null values in `total_laid_off`, `percentage_laid_off`, and `funds_raised_millions`
- Maintained appropriate null values for accurate calculations during analysis

### 4. Data Filtering & Optimization
- Removed records where both `total_laid_off` AND `percentage_laid_off` were NULL
- Dropped temporary `row_num` column used for duplicate identification

## 📈 Key Outcomes
- **Clean, analysis-ready dataset** with 1,843 records
- **Standardized categorical values** across industries and countries
- **Proper data types** for efficient querying and analysis
- **Duplicate-free dataset** ensuring data integrity

## 🚀 Skills Demonstrated
- SQL data manipulation and transformation
- Strategic approach to data cleaning workflows
- Problem-solving for real-world data inconsistencies
- Attention to data quality and integrity
- Database management and optimization

## 📁 File Structure
