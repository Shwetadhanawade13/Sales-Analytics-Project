# Online Retail Dataset Documentation

## Dataset Overview
- **Name**: Online Retail
- **Source**: UCI Machine Learning Repository – [Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)
- **DOI**: https://doi.org/10.24432/C5BW33
- **License**: Creative Commons Attribution 4.0 International (CC BY 4.0)
- **Citation**:
  > Chen, D. (2015). *Online Retail* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33

## Description
The dataset contains all the transactions occurring between 01/12/2010 and 09/12/2011 for a UK based online retailer. Each row represents a single line item in an invoice.

## Coverage
- **Date range**: December 2010 – December 2011 (inclusive)
- **Geography**: United Kingdom (country column may contain other values for returned items)

## Columns
| Column | Description |
|--------|-------------|
| `InvoiceNo` | Invoice number. A leading **'C'** indicates a cancelled transaction. |
| `StockCode` | Product (item) identifier. |
| `Description` | Text description of the product. |
| `Quantity` | Number of units purchased (can be negative for returns). |
| `InvoiceDate` | Date and time of the transaction (format: DD/MM/YYYY HH:MM). |
| `UnitPrice` | Price per unit in British Pounds (£). |
| `CustomerID` | Unique identifier of the customer (may be missing for some rows). |
| `Country` | Country of the customer (mainly `United Kingdom`). |

## Data Quality Notes
- **Missing values**: `CustomerID` may be missing for some transactions. Verify after download.
- **Cancellations & Returns**: Rows with `InvoiceNo` starting with `C` represent cancellations; `Quantity` may be negative for returns.
- **Duplicates**: The raw file may contain duplicate rows; deduplication should be performed as part of data cleaning (Issue 2).

## Download & Storage Instructions
1. Visit the official download page: https://archive.ics.uci.edu/dataset/352/online+retail
2. Click the **Data Folder** link and download `Online Retail.xlsx` (≈22 MB).
3. Save the file to the repository at:
   ```
   data/raw/Online_Retail.xlsx
   ```
4. **Do not** commit the raw Excel file to the repository at this stage. Keep it locally and ensure the path above is used by analysis scripts.

## Usage Guidance
- When loading the dataset in Python (pandas), use:
  ```python
  import pandas as pd
  df = pd.read_excel('data/raw/Online_Retail.xlsx')
  ```
- Validate that the column types match the descriptions above before proceeding with cleaning (Issue 2).

---
*The raw dataset must remain unchanged and excluded from version control. All processing should generate new files under `data/processed/`.*
