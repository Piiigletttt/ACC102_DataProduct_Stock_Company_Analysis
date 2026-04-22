# ACC102_DataProduct_Stock_Company_Analysis
# WRDS Stock Analysis System

## 1. Problem & User

Investors, finance students, and researchers often need a fast way to compare multiple companies using both fundamental and technical indicators.  
This project helps users analyze three selected U.S. stocks through WRDS data by generating valuation tables, profitability metrics, return comparisons, and technical charts.

---

## 2. Data

**Data Source:** WRDS (Wharton Research Data Services)  
**Databases Used:** CRSP + Compustat  
**Access Date:** Real-time when user runs the script

### CRSP Monthly Stock File (crsp.msf)

Key fields:

- htsymbol
- permno
- date
- prc
- ret

Used for:

- Stock price
- Monthly return
- Technical indicators

### Compustat Fundamentals Annual (comp.funda)

Key fields:

- tic
- datadate
- prcc_f
- csho
- ceq
- ni
- dvc

Used for:

- P/E Ratio
- P/B Ratio
- Dividend Yield
- ROE

---

## 3. Methods (main Python steps)

1. Prompt user to input WRDS username and password securely.
2. Ask user to enter three stock tickers.
3. Pull monthly return data from CRSP since 2024-01-01.
4. Calculate industry average monthly return.
5. Pull financial statement data from Compustat.
6. Convert accounting data into monthly observations using forward-fill logic.
7. Calculate:
   - P/E
   - P/B
   - Dividend Yield
   - ROE
8. Compute technical indicators:
   - MA5
   - MA10
   - MA20
   - MA30
   - MACD
9. Generate tables and line charts for comparison.

---

## 4. Key Findings 

- Users can compare three companies’ monthly stock performance against industry average.
- Valuation metrics (P/E, P/B) help identify relative overpricing or undervaluation.
- Dividend Yield highlights shareholder cash return differences.
- ROE shows profitability and management efficiency across firms.
- Moving Average and MACD charts help detect momentum and trend signals.

---

## 5. How to run 

### Example input
WRDS username: yourname
WRDS password: ********
Tickers: AAPL,MSFT,GOOGL

### View Results
The program will automatically generate:

#### Tables
Monthly P/E
Monthly P/B
Monthly Dividend Yield
Monthly ROE
Technical indicator tables
#### Charts
Monthly Return vs Industry Average
P/E Trend vs Industry Average
P/B Trend vs Industry Average
Dividend Yield Trend vs Industry Average
ROE Trend vs Industry Average
Moving Average Charts
MACD Charts

### Exit Program
After analysis is complete, the database connection closes automatically:
"""The database connection has been closed!
"""

## 6. Product link / Demo

## 7. Limitations & next step

### Limitations
1.Requires active WRDS account access.
2.Currently supports only three stocks per run.
3.Uses monthly data rather than daily data.
4.Industry average is based only on selected sample stocks, not full market universe.

###Next Step
1.Add Excel / CSV export
2.Support more stocks
3.Add RSI / Bollinger Bands
4.Add portfolio optimization module
5.Generate automatic PDF reports
