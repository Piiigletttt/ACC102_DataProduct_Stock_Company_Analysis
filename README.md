# ACC102_DataProduct_Stock_Company_Analysis

# WRDS Stock Analysis System

## 1. Project Overview

The WRDS Stock Analysis System is a Python-based financial analytics tool designed for investors, finance students, and researchers who need a fast and structured way to compare multiple U.S. listed companies.

By connecting directly to WRDS (Wharton Research Data Services), the system retrieves real market and accounting data, then automatically generates valuation metrics, profitability indicators, return comparisons, and technical analysis charts.

Users simply enter three stock tickers and the program performs a full comparative analysis.

---

## 2. Target Users

This project is suitable for:

- Investors comparing stock opportunities  
- Finance students learning equity valuation  
- Researchers conducting company performance analysis  
- Beginners exploring financial ratios and technical indicators  

---

## 3. Data Source

**Platform:** WRDS (Wharton Research Data Services)  
**Databases Used:**

- CRSP Monthly Stock File (`crsp.msf`)
- CRSP Header File (`crsp.msfhdr`)
- Compustat Fundamentals Annual (`comp.funda`)

**Data Coverage:** January 2024 to present  
**Access Method:** Real-time query when the script runs

---

## 4. Data Fields Used

## A. CRSP Market Data

Used for stock return and technical analysis.

| Field | Meaning |
|------|---------|
| htsymbol | Stock ticker |
| permno | Security ID |
| date | Trading month |
| prc | Stock price |
| ret | Monthly return |

Used to calculate:

- Monthly return trend
- Industry average return
- Moving averages
- MACD indicators

---

## B. Compustat Fundamental Data

Used for valuation and profitability analysis.

| Field | Meaning |
|------|---------|
| tic | Stock ticker |
| datadate | Financial statement date |
| prcc_f | Fiscal year-end price |
| csho | Shares outstanding |
| ceq | Common equity |
| ni | Net income |
| dvc | Dividends |

Used to calculate:

- P/E Ratio
- P/B Ratio
- Dividend Yield
- ROE

---

## 5. Key Features

## 1. Stock Return Comparison

Compare monthly returns of three selected companies against industry average.

Output:

- Return tables
- Line chart: Monthly Return vs Industry Average

---

## 2. Valuation Analysis

Calculate and compare:

- Price-to-Earnings Ratio (P/E)
- Price-to-Book Ratio (P/B)

Output:

- Monthly tables
- Trend charts

---

## 3. Profitability Analysis

Calculate:

- Return on Equity (ROE)

Output:

- Monthly ROE table
- ROE trend chart

---

## 4. Shareholder Return Analysis

Calculate:

- Dividend Yield

Output:

- Dividend Yield table
- Dividend Yield trend chart

---

## 5. Technical Analysis

Generate common momentum indicators:

- MA5
- MA10
- MA20
- MA30
- MACD
- Signal Line

Output:

- Technical indicator tables
- Moving Average charts
- MACD charts

---

## 6. Calculation Logic

### Financial Ratios

- EPS = Net Income / Shares Outstanding
- BVPS = Common Equity / Shares Outstanding

- P/E = Price / EPS
- P/B = Price / BVPS
- Dividend Yield = Dividend / Price
- ROE = Net Income / Common Equity

### Technical Indicators
- MA5  = 5-period moving average
- MA10 = 10-period moving average
- MA20 = 20-period moving average
- MA30 = 30-period moving average

- MACD = EMA12 - EMA26
- Signal = 9-period EMA of MACD

---

## 7. How to run 

### Step 1 : Install Packages
`pip install wrds pandas matplotlib`

### Step 2 : Run Python File
- Stock Company Analysis.ipynb

### Step 3 : Enter Inputs
```python
Please enter your WRDS username: yourname
Please enter your WRDS password: ********
Please input three companies: AAPL,MSFT,GOOGL
```

---

## 8. Program Output
- After running, the system automatically generates:
```python
### Tables
- Monthly P/E
- Monthly P/B
- Monthly Dividend Yield
- Monthly ROE
- Technical indicator tables

### Charts
- Monthly Return vs Industry Average
- P/E Trend vs Industry Average
- P/B Trend vs Industry Average
- Dividend Yield Trend vs Industry Average
- ROE Trend vs Industry Average
- Moving Average Charts
- MACD Charts
```

### Example Use Case
- Input:
`AAPL`, `MSFT`, `GOOGL`
- The user can compare:
- Which company has stronger profitability
- Which stock looks more expensive
- Which company pays higher dividends
- Which stock has stronger momentum trend

### Exit Program
- After analysis is complete, the database connection closes automatically.

---

## 9. Limitations & next step

### Limitations
- Requires active WRDS account access.
- Currently supports only three stocks per run.
- Uses monthly data rather than daily data.
- Industry average is based only on selected sample stocks, not full market universe.

### Future Improvements
- Add Excel / CSV export
- Support more stocks
- Add RSI / Bollinger Bands
- Add portfolio optimization module
- Generate automatic PDF reports

---

## 10.Technologies Used
- Python
- WRDS API
- Pandas
- Matplotlib

---

## 11.Project Value
- This project combines financial theory + real market data + Python automation into one practical tool.
- It demonstrates skills in:

- Financial data analysis
-  SQL data extraction
- Python programming
- Data visualization
- Investment analytics

---
