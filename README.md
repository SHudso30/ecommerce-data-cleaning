# Data Cleaning Project: Online Retail II Dataset

## Project Overview
This project demonstrates comprehensive data cleaning techniques on the Online Retail II dataset from UCI/Kaggle. The dataset contains transactional data from a UK-based online retailer, with multiple data quality issues that required systematic cleaning.

## Dataset Information
- **Source:** Kaggle - Online Retail II UCI Dataset
- **Original Size:** 1,067,371 rows × 8 columns
- **Final Clean Size:** 779,425 rows × 8 columns
- **Data Retention Rate:** 73%

## Columns
- Invoice: Invoice number
- StockCode: Product code
- Description: Product description
- Quantity: Number of items purchased
- InvoiceDate: Date and time of transaction
- Price: Unit price of product
- Customer ID: Unique customer identifier
- Country: Customer's country

## Data Quality Issues Identified

### 1. Duplicate Records
- **Found:** 34,335 duplicate rows (3.2%)
- **Action:** Removed all duplicates

### 2. Negative Quantities
- **Found:** 22,496 rows with negative quantities (2.18%)
- **Cause:** Returns and cancellations (Invoice codes starting with 'C')
- **Action:** Removed as they represent reversed transactions, not actual sales

### 3. Negative Prices
- **Found:** 5 rows with negative prices (0.00%)
- **Cause:** Data entry errors
- **Action:** Removed invalid records

### 4. Missing Customer IDs
- **Found:** 228,489 missing values (22.77%)
- **Impact:** High percentage of missing customer information
- **Action:** Removed rows without Customer ID as customer analysis requires this field

### 5. Missing Descriptions
- **Found:** 4,382 missing values (0.41%)
- **Impact:** Cannot identify products without descriptions
- **Action:** Removed rows without product descriptions

## Cleaning Process

1. **Load and Explore Data**
   - Imported dataset and examined structure
   - Identified data types and initial issues

2. **Remove Duplicates**
   - Eliminated 34,335 duplicate transactions

3. **Handle Negative Values**
   - Removed negative quantities (returns/cancellations)
   - Removed negative prices (data errors)

4. **Address Missing Values**
   - Removed rows with missing Customer IDs
   - Removed rows with missing Descriptions

5. **Validate Final Dataset**
   - Verified no missing values remain
   - Confirmed all values are valid and positive
   - Checked data types are correct

## Results

### Data Volume Changes
| Stage | Rows | Removed |
|-------|------|---------|
| Original Dataset | 1,067,371 | - |
| After Removing Duplicates | 1,033,036 | 34,335 |
| After Removing Negatives | 1,007,914 | 25,122 |
| Final Clean Dataset | 779,425 | 287,946 |

### Final Data Quality
✅ Zero missing values across all columns  
✅ All quantities are positive integers  
✅ All prices are positive values  
✅ All transactions have valid Customer IDs  
✅ All products have descriptions  
✅ No duplicate records  

## Key Insights
- 27% of original data was problematic and required removal
- Missing Customer IDs were the largest issue (22.77%)
- Returns/cancellations represented 2.18% of transactions
- Clean dataset is now ready for customer segmentation, sales analysis, and predictive modeling

## Tools & Technologies
- **Platform:** Google Colab
- **Language:** Python 3.x
- **Libraries:**
  - pandas - Data manipulation
  - NumPy - Numerical operations
  - matplotlib - Data visualization
  - seaborn - Statistical visualizations

## Files in Repository
- `data_cleaning_project.ipynb` - Jupyter notebook with complete analysis
- `online_retail_cleaned.csv` - Final cleaned dataset
- `README.md` - Project documentation

## How to Run
1. Open the notebook in Google Colab: https://colab.research.google.com/drive/1lhXdSsNQ08pbFQ9OvNQx0XT_MPLqlw7D?usp=sharing
2. Upload the original dataset or use the Kaggle API
3. Run all cells in order
4. Review cleaning steps and visualizations

## Future Improvements
- Add more sophisticated outlier detection
- Implement data validation rules
- Create automated data quality reports
- Add logging for reproducibility

## Author
Sara Hudson
Bachelor's in Data Science  
https://github.com/SHudso30

## Dataset Citation
Daqing Chen, Sai Liang Sain, and Kun Guo, Data mining for the online retail industry: A case study of RFM model-based customer segmentation using data mining, Journal of Database Marketing and Customer Strategy Management, Vol. 19, No. 3, pp. 197â€"208, 2012 (Published online before print: 27 August 2012. doi: 10.1057/dbm.2012.17).

