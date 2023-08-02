# Replication Package for "A new test for unit roots with a partial quadratic trend"


## Overview

This replication package accompanies Yanglin Li, Shaoping Wang, Sainan Jin, and Zhijie Xiao (forthcoming), "A new test for unit roots with a partial quadratic trend", The Econometrics Journal.  The code in this replication package was run with Matlab Release 2018a. Five main files run all of the code to generate the data for the 4 figures and 3 tables in the paper. The replicator should expect the code to run for about 30 hours.

## Data Availability and Provenance Statements

### Statement about Rights

-  I certify that the author(s) of the manuscript have legitimate access to and permission to use the data used in this manuscript. 

### Summary of Availability

-  All data **are** publicly available.

### Details on each Data Source

| Data.Name  | Data.Files | Location | Provided | Citation |
| -- | -- | -- | -- | -- | 
| "Apple Stock prices" | Apple stock price.csv | Data/ | TRUE | Wind（2012）  |
| "Moutai Stock prices" | Moutai Stock prices.csv | Data/ | TRUE |  Wind (2017) |
| "Apple FSCORE” |Apple FSCORE.csv | Data / |  TRUE | Apple Inc. (2012). |
| "Moutai FSCORE” |Moutai FSCORE.csv | Data / |  TRUE | Guizhou Moutai Co., Ltd. (2018).   |
### Example for public use data with required registration and provided extract
- Data on stock prices of **Apple** and **Moutai** were downloaded from the Wind Economic Database (https://www.wind.com.cn/portal/zh/EDB/index.html). A copy of the data is
provided as part of this archive. The data are in the public domain.

Datafile:  `Data/Apple stock price.csv` and `Data/Moutai stock price.csv`
### Example for public use data collected by the authors
- Data on EPS, ROE, and dividends used to support the findings of this study were collected  by the authors, and are available from quarterly and annual financial statements published by listed
companies (**Moutai**： https://www.moutaichina.com/maotaigf/tzzgx/cwbg/ and **Apple**  https://investor.apple.com/sec-filings/default.aspx ).
- Data about **FSCORE** is calculated based on the method proposed by Piotroski (2000) using financial data from both Apple and Maotai companies. The calculation process and results can be found in `Data/Moutai FSCORE.csv` and `Data/Apple FSCORE.csv`

## Dataset list


| Data file | Source | Notes    |Provided |
|-----------|--------|----------|---------|
| `mydata.xls` | Data on stock prices of **Apple** and **Moutai** | To merge "Apple stock price.csv" and "Moutai Stock prices.csv" into one Excel file with different sheets | Yes|
 

## Computational requirements


### Software Requirements

- Matlab (code was run with Matlab Release 2020a)

Portions of the code use Powershell scripting, which may require Windows 10 or higher.

### Controlled Randomness
-  Random seed is set at line __6__ of each program  __DGP_Figure_1.m__, __table_1.m__, __table_2.m__, __figure_2.m__, and __empirical.m__.

### Memory and Runtime Requirements

#### Summary

Approximate time needed to reproduce the analyses on a standard (CURRENT YEAR) desktop machine:

- 8-24 hours

#### Details


Portions of the code were last run on a **32-core Intel server with 64 GB of RAM, 2 TB of fast local storage**. The computation took 15 hours. 


## Description of programs/code

- Each _ADF_ program in the respective folder (e.g., `Programs/Table_1/ADF.m`) is a function designed to perform the calculation for the Augmented Dickey-Fuller (ADF) statistic with different information criteria and testing forms.
- Each _ADF_lag_ program in each folder (e.g., `Programs/Table_1/ADF_lag.m`) is a function used to calculate the lag order required for the Augmented Dickey-Fuller (ADF) test.
- Each _detrend_ program in the respective folders (e.g., `Programs/Table_1/detrend.m`) is a function used to detrend the data by using the local generalized least squares (GLS) detrending method. When the input variable type is 1, the model is a process with a partial quadratic trend, and When the input variable type is 2, the model is the process with a break in the slope of the linear trend. 
- Each _found_tau_ program in the respective folders (e.g., `Programs/Table_1/found_tau.m`) is a function used to estimate the break fraction by minimizing the sum of the squared residuals from the GLS-detrended regression.
- Each _myols_ program in the respective folders (e.g., `Programs/Table_1/myols.m`) is a function used for conducting least squares regression estimation. It returns various coefficient statistics, residual terms, and other relevant results.
- Each _URQ_ program in each folder (e.g., `Programs/Table_1/URQ.m`) is a function used to calculate the URQ test statistics which is proposed by the manuscript.
- Each _cv_URQ_ program in the respective folders (e.g., `Programs/Table_1/cv_URQ.m`) is a function used to calculate the critical values for the URQ test.
- Each _ SADF_ program in the respective folders (e.g., `Programs/Empirical/SADF.m`) is a function used to compute the SADF (Supremum Augmented Dickey-Fuller) test statistics as proposed by Phillips et al. (2015a, b).
- Each _cv_SADF_ program in the respective folders (e.g., `Programs/Empirical/cv_SADF.m`) is a function used to simulate the finite sample critical values for the SADF test.
- Program  _ChowDF_ in `Programs/Table_2/ChowDF.m` is a function used to compute the Chow-DF test statistics as proposed by Homm and Breitung (2012).
- Program  _ADF_Chow_ in `Programs/Table_2/ADF_Chow.m` is a function used to compute the Chow-type DF test statistics.
- Program  _GSADF _ in `Programs/Table_2/GSADF.m` is a function used to compute the generalized SADF (GSADF) test statistics as proposed by Phillips et al. (2015a,b).
- Programs in `Programs/Figure_1/DGP_Figure_1.m` will generate Figure 1 in the manuscript. Output files are called an appropriate name (figure_1.fig) and should be easy to correlate with the manuscript.
- Programs in `Programs/Table_1/table_1.m` will generate Table 1 in the main body of the manuscript. Output files are called an appropriate name (result_size_power.mat) and should be easy to correlate with the manuscript.
- Programs in `Programs/Figure_2/figure_2.m` generate Figure 2 in the manuscript.  Output files are called an appropriate name (figure2_1.fig, figure2_2.fig, and figure2_3.fig) and should be easy to correlate with the manuscript.
- Programs in `Programs/Table_2/table_2.m` generate Table 2 in the manuscript. Output files are called an appropriate name (DBF_SADF_T400.mat) and should be easy to correlate with the manuscript.
- Programs in `programs/Empirical/empirical.m ` generate the results of Figure 3, Table 3, and Table 4 in the manuscript. Output files are called an appropriate name (figure_3_Kweichow_Moutai.fig, figure_3_Apple.fig, result_table_3.mat and result_table_4.mat) and should be easy to correlate with the manuscript.

## Instructions to Replicators

- Open Matlab Software: Open the Matlab software on your computer.
- Open the Main Program File: Navigate to the folder corresponding to the table and open the Matlab script (not a function file) that contains the main program code. For example, open programs/Table_1 and find the main program programs/Table_1/table_1.m.
- Run the Main Program: In the Matlab editor, click the "Run" button (usually represented by a green arrow icon) or use the shortcut key (typically F5) to execute the main program. Matlab will execute the code in the program sequentially.
- View the Output: After the program has finished running, examine the output results generated by the program.

### Details

- `Programs/Empirical/empirical.m`: It will create all outputs in the Empirical application section except for tables 5 and 6, and it can automatically invoke other MATLAB functions within this folder.
   - If you wish to calculate results for other data (e.g., other stock prices) to be tested, you can replace the data file by changing the parameter "num" to the name of the data being tested and updating the data in the mydata.xls file.
- `Programs/Figure_2/figure_2.m`: It will generate the three subfigures in Figure 2 of the manuscript, and it also involves automatically invoking other MATLAB functions within this folder.
   - If you want to plot power curves for other break fractions and corresponding sample lengths, you can change the parameters "tau" and "T."
- `Programs/Table_1/table_1.m`: It will generate Table 1 in the manuscript, and it involves automatically invoking other MATLAB functions within this folder.
- `Programs/Table_2/table_2.m`: It will generate Table 2 in the manuscript, and it involves automatically invoking other MATLAB functions within this folder.
   - The entire process should take about 12 hours.

## List of tables and programs
The provided code reproduces:

-  Selected tables and figures in the paper, as explained and justified below.


| Figure/Table     | Program                  |  Output file    or    Source                                   |                                                                                                                       
|-------------------|--------------------------|-------------------------------------------------------|
| Table 1           | Programs/Table_1/table_1.m        | result_size_power.mat                                 |                                                                                                                                                          
| Table 2           | Programs/Table_2/table_2.m        | DBF_SADF_T400.mat                                     |                                                                                                                           
| Table 3           | Programs/Empirical/empirical.m    | result_table_3.mat                                    |                                                                                                                           
| Table 4           | Programs/Empirical/empirical.m    | result_table_4.mat                                    |                                                                                                                         
| Table 5 and Table 6          | n.a. (no data)           |           Source：https://www.moutaichina.com/maotaigf/tzzgx/cwbg/ and https://investor.apple.com/sec-filings/default.aspx     |                                        
| Figure 1          | Programs/Figure_1/DGP_Figure_1.m           | figure_1.fig                                          |                                                                                                                           
| Figure 2          | Programs/Empirical/empirical.m    | figure2_1.fig, figure2_2.fig and figure2_3.fig           |                                                                                                                              
| Figure 3          | Programs/Empirical/empirical.m    | figure_3_Kweichow_Moutai.fig and figure_3_Apple.fig      |                                                                                                                           

## References

Apple Inc. (2012). Quarterly Financial Reports from Q4 2010 to Q2 2012. Apple Inc. Investor Relations. https://investor.apple.com/sec-filings/default.aspx (Accessed July 6, 2023).

Guizhou Moutai Co., Ltd. (2018). Quarterly Financial Reports from Q3 2016 to Q1 2018. Guizhou Moutai Company Official. https://www.moutaichina.com/maotaigf/tzzgx/cwbg/ (Accessed July 6, 2023).

Homm, U. and J. Breitung (2012). Testing for speculative bubbles in stock markets: a comparison of alternative methods. Journal of Financial Econometrics, 10(1), 198–231.

Piotroski, J. D. (2000). Value investing: The use of historical financial statement information to separate winners from losers. Journal of Accounting Research, 1–41.

Phillips, P. C. B., S. Shi, and J. Yu (2015a). Testing for multiple bubbles: Historical episodes of exuberance and collapse in the s&p 500. International Economic Review 56(4), 1043–1078.

Phillips, P. C. B., S. Shi, and J. Yu (2015b). Testing for multiple bubbles: Limit theory of real‐time detectors. International Economic Review 56(4), 1079–1134.

WIND. (2012). Apple Inc. Daily Stock Prices from October 1, 2010 to April 9, 2012. WIND Financial Database. https://www.wind.com.cn/portal/zh/EDB/index.html (Accessed July 1, 2013).

WIND. (2017). Guizhou Moutai Co., Ltd. Daily Stock Prices from April 1, 2016 to November 16, 2017. WIND Financial Database. https://www.wind.com.cn/portal/zh/EDB/index.html (Accessed July 1, 2018).

 

