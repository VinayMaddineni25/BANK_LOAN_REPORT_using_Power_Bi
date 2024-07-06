## **Problem Statement:**

**Objective:**
To analyze and interpret the bank loan data to understand the performance of the bank's loan issuance, identify trends, and pinpoint areas for improvement in loan management.

### Steps followed


### Step 1: Set Up the Database Connection
1. **Open SQL Server Management Studio (SSMS) :**
   - Launch SSMS and connect to your SQL Server instance.

2. **Create a New Database:**
3. **Import Data into the `financial_loan` Table:**
   - Prepare your data in a suitable format (e.g., a `.csv` file).
   - Use the SQL Server Import and Export Wizard in SSMS:
     - Right-click on the `Bank loan DB` database.
     - Select `Tasks > Import Data`.
     - Follow the wizard steps to import data from your source file into the

### Step 2: Execute the Queries for the Summary Report
1. **Total Loan Applications**
    ```sql
    SELECT COUNT(id) AS Total_Loan_Applications FROM financial_loan;
    ```
![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/4bd36a54-f491-4cd0-b52f-bb47e14ec0af)

2. **MTD Loan Applications**
    ```sql
    SELECT COUNT(id) AS Total_Loan_Applications FROM financial_loan
    WHERE MONTH(issue_date) = 12 AND YEAR(issue_date) = 2021;
    ```
![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/51f250da-56a4-476c-8f9a-d8728ccb6233)

3. **PMTD Loan Applications**
    ```sql
    SELECT COUNT(id) AS PMTD_Total_Loan_Applications FROM financial_loan
    WHERE MONTH(issue_date) = 11 AND YEAR(issue_date) = 2021;
    ```
![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/b54a5aab-d7b7-40eb-ae4a-76707f500874)


4. **Total Funded Amount**
    ```sql
    SELECT SUM(loan_amount) AS Total_Funded_Amount FROM financial_loan;
    ```
![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/89a896dc-f2fb-4a7b-905e-cdb9881124e2)


5. **MTD Total Funded Amount**
    ```sql
    SELECT SUM(loan_amount) AS MTD_Total_Funded_Amount FROM financial_loan
    WHERE MONTH(issue_date) = 12 AND YEAR(issue_date) = 2021;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/de8df2d8-3f44-4424-94fb-31bb5ad21518)


6. **PMTD Total Funded Amount**
    ```sql
    SELECT SUM(loan_amount) AS PMTD_Total_Funded_Amount FROM financial_loan
    WHERE MONTH(issue_date) = 11 AND YEAR(issue_date) = 2021;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/d23316c2-e27d-4389-b59a-b65c9019c93d)

7. **Total Amount Received**
    ```sql
    SELECT SUM(total_payment) AS Total_Amount_Received FROM financial_loan;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/82ec075b-ab5b-4209-88ec-3304d7369c0a)


8. **MTD Total Amount Received**
    ```sql
    SELECT SUM(total_payment) AS MTD_Total_Amount_Received FROM financial_loan
    WHERE MONTH(issue_date) = 12 AND YEAR(issue_date) = 2021;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/893dfe3a-6af0-45fd-964a-e72a6eab30f1)


9. **PMTD Total Amount Received**
    ```sql
    SELECT SUM(total_payment) AS PMTD_Total_Amount_Received FROM financial_loan
    WHERE MONTH(issue_date) = 11 AND YEAR(issue_date) = 2021;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/88c4eb4f-82bf-46ea-bc6c-7a83633b4718)


10. **Average Interest Rate**
    ```sql
    SELECT ROUND(AVG(int_rate), 4)*100 AS Avg_Int_Rate FROM financial_loan;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/3bc32e18-a87c-4327-aaad-82cdb051580d)


11. **MTD Average Interest Rate**
    ```sql
    SELECT ROUND(AVG(int_rate), 4)*100 AS MTD_Avg_Int_Rate FROM financial_loan
    WHERE MONTH(issue_date) = 12 AND YEAR(issue_date) = 2021;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/ca14c545-4a63-4d21-bba4-c4b39cd26c23)


12. **PMTD Average Interest Rate**
    ```sql
    SELECT ROUND(AVG(int_rate), 4)*100 AS PMTD_Avg_Int_Rate FROM financial_loan
    WHERE MONTH(issue_date) = 11 AND YEAR(issue_date) = 2021;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/29e06ff0-fcf0-4303-b35f-b82ea65b1413)


13. **Avg DTI**
    ```sql
    SELECT ROUND(AVG(dti), 4)*100 AS Avg_DTI FROM financial_loan;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/30e6878e-9ece-4269-86dc-44c4c285ab60)


14. **MTD Avg DTI**
    ```sql
    SELECT ROUND(AVG(dti), 4)*100 AS MTD_Avg_DTI FROM financial_loan
    WHERE MONTH(issue_date) = 12 AND YEAR(issue_date) = 2021;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/edfbe58c-7a8e-459a-85bf-875c3e3bd999)


15. **PMTD Avg DTI**
    ```sql
    SELECT ROUND(AVG(dti), 4)*100 AS PMTD_Avg_DTI FROM financial_loan
    WHERE MONTH(issue_date) = 11 AND YEAR(issue_date) = 2021;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/6e1ca6b0-38e9-46d2-a53b-6aa887345e45)


16. **Good Loan Percentage**
    ```sql
    SELECT
        (COUNT(CASE WHEN loan_status = 'Fully Paid' OR loan_status = 'Current' THEN id END) * 100) / 
        COUNT(id) AS Good_Loan_Percentage
    FROM financial_loan;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/7c605a4e-452c-4529-b5ea-3fb8492ace71)


17. **Good Loan Applications**
    ```sql
    SELECT COUNT(id) AS Good_Loan_Applications FROM financial_loan
    WHERE loan_status = 'Fully Paid' OR loan_status = 'Current';
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/e5c37195-74e3-4c25-ba38-594d036bcba0)


18. **Good Loan Funded Amount**
    ```sql
    SELECT SUM(loan_amount) AS Good_Loan_Funded_amount FROM financial_loan
    WHERE loan_status = 'Fully Paid' OR loan_status = 'Current';
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/c9d80269-4dde-4a45-a780-ddefb2273677)


19. **Good Loan Amount Received**
    ```sql
    SELECT SUM(total_payment) AS Good_Loan_amount_received FROM financial_loan
    WHERE loan_status = 'Fully Paid' OR loan_status = 'Current';
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/e3703d8b-ee80-420e-af90-afb4d5840480)


20. **Bad Loan Percentage**
    ```sql
    SELECT
        (COUNT(CASE WHEN loan_status = 'Charged Off' THEN id END) * 100.0) / 
        COUNT(id) AS Bad_Loan_Percentage
    FROM financial_loan;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/3055cd9e-1969-48b3-be83-5c604730af07)


21. **Bad Loan Applications**
    ```sql
    SELECT COUNT(id) AS Bad_Loan_Applications FROM financial_loan
    WHERE loan_status = 'Charged Off';
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/b4522c7f-3c0f-472a-810d-091e876c8d45)


22. **Bad Loan Funded Amount**
    ```sql
    SELECT SUM(loan_amount) AS Bad_Loan_Funded_Amount FROM financial_loan
    WHERE loan_status = 'Charged Off';
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/7eaef905-b909-4e40-a4c7-617dd15291d4)


23. **Bad Loan Amount Received**
    ```sql
    SELECT SUM(total_payment) AS Bad_Loan_amount_received FROM financial_loan
    WHERE loan_status = 'Charged Off';
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/8a4419b5-4d21-406e-862d-a7e3ff58c5ca)


24. **Loan Status Overview**
    ```sql
    SELECT
        loan_status,
        COUNT(id) AS Total_Loan_Applications,
        SUM(total_payment) AS Total_Amount_Received,
        SUM(loan_amount) AS Total_Funded_Amount,
        AVG(int_rate * 100) AS Interest_Rate,
        AVG(dti * 100) AS DTI
    FROM financial_loan
    GROUP BY loan_status;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/e886796a-4694-4232-a849-6e91590d56c0)


25. **MTD Loan Status Overview**
    ```sql
    SELECT 
        loan_status, 
        SUM(total_payment) AS MTD_Total_Amount_Received, 
        SUM(loan_amount) AS MTD_Total_Funded_Amount 
    FROM financial_loan
    WHERE MONTH(issue_date) = 12 
    GROUP BY loan_status;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/fe68ef86-af34-492c-b5a0-bd30ee372e01)


### Step 3: Execute the Queries for the Overview Report
1. **Monthly Loan Applications**
    ```sql
    SELECT 
        MONTH(issue_date) AS Month_Number, 
        DATENAME(MONTH, issue_date) AS Month_name, 
        COUNT(id) AS Total_Loan_Applications,
        SUM(loan_amount) AS Total_Funded_Amount,
        SUM(total_payment) AS Total_Amount_Received
    FROM financial_loan
    GROUP BY MONTH(issue_date), DATENAME(MONTH, issue_date)
    ORDER BY MONTH(issue_date);
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/4c0282e8-5be9-46a0-aad9-b29a80675d2f)


2. **State-wise Loan Applications**
    ```sql
    SELECT 
        address_state AS State, 
        COUNT(id) AS Total_Loan_Applications,
        SUM(loan_amount) AS Total_Funded_Amount,
        SUM(total_payment) AS Total_Amount_Received
    FROM financial_loan
    GROUP BY address_state
    ORDER BY address_state;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/57649127-a024-4bad-ac4d-751cfb3cb95e)


3. **Term-wise Loan Applications**
    ```sql
    SELECT 
        term AS Term, 
        COUNT(id) AS Total_Loan_Applications,
        SUM(loan_amount) AS Total_Funded_Amount,
        SUM(total_payment) AS Total_Amount_Received
    FROM financial_loan
    GROUP BY term
    ORDER BY term;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/fc38d926-437b-4090-a9d0-e442d5a2e54b)


4. **Employee Length-wise Loan Applications**
    ```sql
    SELECT 
        emp_length AS Employee_Length, 
        COUNT(id) AS Total_Loan_Applications,
        SUM(loan_amount) AS Total_Funded_Amount,
        SUM(total_payment) AS Total_Amount_Received
    FROM financial_loan
    GROUP BY emp_length
    ORDER BY COUNT(id) DESC;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/b3ae7966-5482-426d-9fc7-68d91df60fcd)


5. **Purpose-wise Loan Applications**
    ```sql
    SELECT 
        purpose AS Purpose, 
        COUNT(id) AS Total_Loan_Applications,
        SUM(loan_amount) AS Total_Funded_Amount,
        SUM(total_payment) AS Total_Amount_Received
    FROM financial_loan
    GROUP BY purpose
    ORDER BY COUNT(id) DESC;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/6464d16c-31b2-4c4a-9885-87639d25d30e)


6. **Home Ownership-wise Loan Applications**
    ```sql
    SELECT 
        home_ownership AS Home_Ownership, 
        COUNT(id) AS Total_Loan_Applications,
        SUM(loan_amount) AS Total_Funded_Amount,
        SUM(total_payment) AS Total_Amount_Received
    FROM financial_loan
    GROUP BY home_ownership
    ORDER BY COUNT(id) DESC;
    ```
    ![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/dba98269-4780-415f-822c-2d99d2ac201a)


### Step 4: Apply Filters (Optional)
- Modify the above queries to apply filters based on specific criteria (e.g., Grade A loans, specific states, etc.).
- Compare the filtered results with the overall results to draw insights.

### Step 5: Compile the Report
- Collect the results from all the queries and compile them into a structured report.
- Visualize the data using charts, graphs, and tables for better understanding and presentation.

### Step 6: Analyze the Results
- Analyze the compiled data to identify trends, patterns, and areas for improvement.
- Use the insights to make data-driven decisions for enhancing the bank's loan portfolio performance.

### Step 7: Import Data from SQL Server into Power BI

1. Open Power BI.
2. Select `Get Data > SQL Server`.
3. Connect to your SQL Server instance and select the `Bank loan DB` database.

### Step 8: Data Check
Before analyzing data go check quality of data
(Goto --> Home -->  Transform data) this will open a new window power query  editor and go for column quality and check for error and empty / null values in the table
Most important things in the data to check are column quality and column distribution

### Step 9: Create the Date Table
- In the "Modeling" tab, click on "New Table".
- Enter the following DAX expression to create a Date Table:
    ```DAX
    Date Table = CALENDAR(MIN(financial_loan[issue_date]), MAX(financial_loan[issue_date]))
    ```
- This will create a calendar table that spans from the minimum to the maximum issue date in the `financial_loan` table.

### Step 10: Create Measures for Loan Applications
- In the "Modeling" tab, click on "New Measure".
- Create the following measures one by one:

    ```DAX
    Total Loan Applications = COUNT(financial_loan[id])
    ```

    ```DAX
    MTD Loan Applications = CALCULATE(TOTALMTD([Total Loan Applications], 'Date Table'[Date]))
    ```

    ```DAX
    PMTD Loan Applications = CALCULATE([Total Loan Applications], DATESMTD(DATEADD('Date Table'[Date], -1, MONTH)))
    ```

    ```DAX
    MoM Loan Applications = ([MTD Loan Applications] - [PMTD Loan Applications]) / [PMTD Loan Applications]
    ```

### Step 11: Create Measures for Funded Amount
- Continue creating the measures for the funded amount:

    ```DAX
    Total Funded Amount = SUM(financial_loan[loan_amount])
    ```

    ```DAX
    MTD Funded Amount = CALCULATE(TOTALMTD([Total Funded Amount], 'Date Table'[Date]))
    ```

    ```DAX
    PMTD Funded Amount = CALCULATE([Total Funded Amount], DATESMTD(DATEADD('Date Table'[Date], -1, MONTH)))
    ```

    ```DAX
    MoM Total Funded Amount = ([MTD Funded Amount] - [PMTD Funded Amount]) / [PMTD Funded Amount]
    ```

### Step 12: Create Measures for Amount Received
- Create the measures for the total amount received:

    ```DAX
    Total Amount Received = SUM(financial_loan[total_payment])
    ```

    ```DAX
    MTD Total Amount Received = CALCULATE(TOTALMTD([Total Amount Received], 'Date Table'[Date]))
    ```

    ```DAX
    PMTD Total Amount Received = CALCULATE([Total Amount Received], DATESMTD(DATEADD('Date Table'[Date], -1, MONTH)))
    ```

    ```DAX
    MoM Total Amount Received = ([MTD Total Amount Received] - [PMTD Total Amount Received]) / [PMTD Total Amount Received]
    ```

### Step 13: Create Measures for Average Interest Rate
- Create the measures for the average interest rate:

    ```DAX
    Avg Interest Rate = AVERAGE(financial_loan[int_rate])
    ```

    ```DAX
    MTD Avg Interest Rate = CALCULATE(TOTALMTD([Avg Interest Rate], 'Date Table'[Date]))
    ```

    ```DAX
    PMTD Avg Interest Rate = CALCULATE([Avg Interest Rate], DATESMTD(DATEADD('Date Table'[Date], -1, MONTH)))
    ```

    ```DAX
    MoM Avg Interest Rate = ([MTD Avg Interest Rate] - [PMTD Avg Interest Rate]) / [PMTD Avg Interest Rate]
    ```

### Step 14: Create Measures for Average DTI
- Create the measures for the average debt-to-income (DTI) ratio:

    ```DAX
    Avg DTI = AVERAGE(financial_loan[dti])
    ```

    ```DAX
    MTD Avg DTI = CALCULATE(TOTALMTD([Avg DTI], 'Date Table'[Date]))
    ```

    ```DAX
    PMTD Avg DTI = CALCULATE([Avg DTI], DATESMTD(DATEADD('Date Table'[Date], -1, MONTH)))
    ```

    ```DAX
    MoM Avg DTI = ([MTD Avg DTI] - [PMTD Avg DTI]) / [PMTD Avg DTI]
    ```

### Step 15: Create Measures for Good and Bad Loans
- Create the measures for good loans:

    ```DAX
    Good Loan % = (CALCULATE([Total Loan Applications], financial_loan[Good vs Bad Loan] = "Good Loan")) / [Total Loan Applications]
    ```

    ```DAX
    Good Loan Applications = CALCULATE([Total Loan Applications], financial_loan[Good vs Bad Loan] = "Good Loan")
    ```

    ```DAX
    Good Loan Funded Amount = CALCULATE([Total Funded Amount], financial_loan[Good vs Bad Loan] = "Good Loan")
    ```

    ```DAX
    Good Loan Total Received = CALCULATE([Total Amount Received], financial_loan[Good vs Bad Loan] = "Good Loan")
    ```

- Create the measures for bad loans:

    ```DAX
    Bad Loan % = (CALCULATE([Total Loan Applications], financial_loan[Good vs Bad Loan] = "Bad Loan")) / [Total Loan Applications]
    ```

    ```DAX
    Bad Loan Applications = CALCULATE([Total Loan Applications], financial_loan[Good vs Bad Loan] = "Bad Loan")
    ```

    ```DAX
    Bad Loan Funded Amount = CALCULATE([Total Funded Amount], financial_loan[Good vs Bad Loan] = "Bad Loan")
    ```

    ```DAX
    Bad Loan Received Amount = CALCULATE([Total Amount Received], financial_loan[Good vs Bad Loan] = "Bad Loan")
    ```

### Step 16: Build the Report
- Drag and drop the measures onto your report canvas to create visuals like cards, charts, and tables.
- Use slicers and filters to enable dynamic interaction with the report.
- Format the visuals for better readability and presentation.

### Step 17: Publish the Report
- Once the report is ready, publish it to the Power BI service for sharing with stakeholders.

###DASHBOARDS

![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/0d9e0e54-47fc-4f54-bcda-98b828a63df8)

![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/d99c61c6-b96c-487a-b662-bb143f32a6cb)

![image](https://github.com/VinayMaddineni25/BANK_LOAN_REPORT_using_Power_Bi/assets/71554745/e78e69f6-e5ef-4268-b515-fa86260a487f)

## Insights and Summary

### DASHBOARD 1: SUMMARY

#### Key Performance Indicators (KPIs)

**Total Loan Applications:**
- **Insight:** Monitoring the total number of loan applications helps gauge demand for loans. 
- **Metric:** `Total Loan Applications`
- **Sub-metrics:**
  - `MTD Loan Applications`
  - `MoM Loan Applications`
- **Action:** High application volumes may indicate increased marketing success or economic conditions prompting more borrowing. Conversely, low volumes might trigger a review of loan products or marketing strategies.

**Total Funded Amount:**
- **Insight:** Tracking the total funded amount helps assess how much money is being lent out.
- **Metric:** `Total Funded Amount`
- **Sub-metrics:**
  - `MTD Funded Amount`
  - `MoM Funded Amount`
- **Action:** Significant changes in funded amounts could reflect shifts in credit policy, economic conditions, or competitive landscape.

**Total Amount Received:**
- **Insight:** This indicates the cash flow from loan repayments.
- **Metric:** `Total Amount Received`
- **Sub-metrics:**
  - `MTD Total Amount Received`
  - `MoM Total Amount Received`
- **Action:** High collection rates suggest healthy repayment behavior, whereas low collection rates might indicate rising default risk or issues with loan servicing.

**Average Interest Rate:**
- **Insight:** This metric reveals the average cost of borrowing for the customers.
- **Metric:** `Avg Interest Rate`
- **Sub-metrics:**
  - `MTD Avg Interest Rate`
  - `MoM Avg Interest Rate`
- **Action:** Changes in average interest rates could be due to adjustments in pricing strategy or shifts in the risk profile of borrowers.

**Average Debt-to-Income Ratio (DTI):**
- **Insight:** DTI is a critical measure of borrower financial health.
- **Metric:** `Avg DTI`
- **Sub-metrics:**
  - `MTD Avg DTI`
  - `MoM Avg DTI`
- **Action:** High DTI ratios might suggest that borrowers are over-leveraged, which could increase default risk.

#### Good Loan vs. Bad Loan KPIs

**Good Loan:**
- **Insight:** Assessing the performance and quality of loans classified as "Good".
- **Metrics:**
  - `Good Loan %`
  - `Good Loan Applications`
  - `Good Loan Funded Amount`
  - `Good Loan Total Received`
- **Action:** High percentages and amounts here indicate a healthy loan portfolio.

**Bad Loan:**
- **Insight:** Evaluating loans classified as "Bad" to identify potential risks.
- **Metrics:**
  - `Bad Loan %`
  - `Bad Loan Applications`
  - `Bad Loan Funded Amount`
  - `Bad Loan Received Amount`
- **Action:** Increasing bad loan metrics may prompt a review of lending criteria and risk management practices.

#### Loan Status Grid View
- **Insight:** Provides a detailed breakdown of loan metrics by status.
- **Metrics:**
  - `Total Loan Applications`
  - `Total Funded Amount`
  - `Total Amount Received`
  - `MTD Funded Amount`
  - `MTD Amount Received`
  - `Average Interest Rate`
  - `Average DTI`
- **Action:** This view helps identify trends and issues across different loan statuses, facilitating targeted interventions.

### DASHBOARD 2: OVERVIEW

**Monthly Trends by Issue Date (Line Chart):**
- **Insight:** Identifying seasonality and long-term trends.
- **Metrics:**
  - `Total Loan Applications`
  - `Total Funded Amount`
  - `Total Amount Received`
- **Action:** Helps in planning and forecasting based on historical trends.

**Regional Analysis by State (Filled Map):**
- **Insight:** Understanding geographic distribution of lending activities.
- **Metrics:**
  - `Total Loan Applications`
  - `Total Funded Amount`
  - `Total Amount Received`
- **Action:** Regional disparities may prompt localized marketing or policy adjustments.

**Loan Term Analysis (Donut Chart):**
- **Insight:** Distribution of loans across various term lengths.
- **Metrics:**
  - `Total Loan Applications`
  - `Total Funded Amount`
  - `Total Amount Received`
- **Action:** Insights into popular loan terms can inform product development and marketing.

**Employee Length Analysis (Bar Chart):**
- **Insight:** Impact of employment history on loan applications.
- **Metrics:**
  - `Total Loan Applications`
  - `Total Funded Amount`
  - `Total Amount Received`
- **Action:** Useful for risk assessment and tailoring loan products.

**Loan Purpose Breakdown (Bar Chart):**
- **Insight:** Understanding reasons for borrowing.
- **Metrics:**
  - `Total Loan Applications`
  - `Total Funded Amount`
  - `Total Amount Received`
- **Action:** Can influence marketing strategies and product offerings.

**Home Ownership Analysis (Tree Map):**
- **Insight:** Impact of home ownership on loan metrics.
- **Metrics:**
  - `Total Loan Applications`
  - `Total Funded Amount`
  - `Total Amount Received`
- **Action:** Home ownership status can be a key risk factor in lending decisions.

### DASHBOARD 3: DETAILS

**GRID**
- **Insight:** A comprehensive and detailed view of all key metrics.
- **Objective:** Provide a user-friendly interface for accessing detailed loan data.
- **Metrics:**
  - `Total Loan Applications`
  - `Total Funded Amount`
  - `Total Amount Received`
  - `MTD Funded Amount`
  - `MTD Amount Received`
  - `Average Interest Rate`
  - `Average DTI`
- **Action:** This dashboard will serve as a single source for detailed loan data, aiding in deep analysis and informed decision-making.

---

### Summary
The outlined dashboards and their respective KPIs provide a robust framework for analyzing the bank's loan portfolio. By monitoring these metrics, the bank can gain valuable insights into loan demand, funding activities, repayment patterns, borrower risk profiles, and overall portfolio health. This data-driven approach will enable the bank to make informed strategic decisions, optimize lending practices, and mitigate risks effectively.
