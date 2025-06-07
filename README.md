Banking Risk Analytics Dashboard

This project focuses on analyzing banking data to understand and mitigate risk in lending using Power BI dashboards. It includes extensive data cleaning, transformation, and KPI development to assist banks in making data-driven decisions about client loans and deposits.

Problem Statement

Develop an analytical dashboard that helps banks minimize risk while lending by analyzing client profiles, deposit history, loan amounts, and engagement with banking services.

Solution Overview

By using Power BI and custom data modeling techniques, we created an interactive banking dashboard that displays key performance indicators (KPIs) such as:

•	Total Loan

•	Total Clients

•	Total Deposits

•	Total Fees

•	Loan Distribution by Income Band & Nationality

•	Engagement Metrics

The dashboard empowers decision-makers to visualize risk profiles and evaluate client eligibility for banking services, particularly loans.

Dataset

The dataset includes multiple interrelated tables such as:

•	Banking Relationship

•	Client-Banking

•	Gender

•	Investment Advisor

•	Period

Source

Internal structured dataset (CSV/Excel format) reflecting client-banking relationships.

Data Cleaning & Feature Engineering

Several derived columns and transformations were applied:

•	Engagement Timeframe: Duration of the client’s relationship with the bank.

•	Engagement Days: Calculated using DATEDIFF to measure active banking period.

•	Income Band: Bucketed estimated incomes into “Low”, “Mid”, etc.

•	Processing Fees: Added as a function of fee structure (e.g., 5% if “High”).

Key Metrics & DAX Functions

KPI	Description	DAX Example
Total Clients	Count of unique clients	DISTINCTCOUNT('Clients - Banking'[Client ID])

Total Loan	Combined loan amount	[Bank Loan] + [Business Lending] + [Credit Cards Balance]

Total Deposit	Sum of all account deposits	[Bank Deposit] + [Savings Account] + [Checking Accounts] + [Foreign Currency Account]

Total Fees	Calculated from loan and processing fees	SUMX('Clients - Banking', [Total Loan] * [Processing Fees])

Engagement Account	Total client-bank relationship days	SUM('Clients - Banking'[Engagement Days])

Visualizations

The Power BI Dashboard consists of the following pages:
1.	Home Page: Navigation and summary.
2.	Loan Analysis: Visual breakdown of loan distributions.
3.	Deposit Analysis: Insights on total deposits and account types.
4.	KPI Dashboard: Interactive tiles for all key metrics.
5.	Summary Dashboard: Aggregated view of banking metrics.

Dashboard Snapshots

![image](https://github.com/user-attachments/assets/796e41d5-f117-4ef0-93c8-15f441645304)
![image](https://github.com/user-attachments/assets/d8d46aca-050f-4508-a49e-4cc3975fced8)

Project Structure

Banking-Risk-Analytics
├── Banking.csv               # Main cleaned dataset

├── Banking.xlsx              # Structured data source

├── clients.csv               # Client-specific data

├── BankEDA.ipynb            # Jupyter notebook for initial analysis

├── Banking Dashboard.pbix    # Final Power BI dashboard

├── Banking Report.docx       # Project documentation and insights

├── Banking.pptx              # Summary presentation

└── README.md                 # Project overview (this file)

Requirements

No Python packages are strictly required unless you're running BankEDA.ipynb for exploratory analysis. In that case:
•	pandas

•	matplotlib / seaborn

•	jupyter

Power BI Desktop (latest version) is required to view/edit .pbix dashboard.

How to Use

1.	Clone the repository:
git clone https://github.com/mukund06s
2.	Open Banking Dashboard.pbix in Power BI Desktop.
3.	Explore the interactive visuals.
4.	(Optional) Run the BankEDA.ipynb notebook for preliminary EDA.

Future Enhancements

•	Integrate predictive models to forecast loan default risk.

•	Add real-time database connectivity.

•	Enable web embedding or export dashboards as web apps.

Conclusion

This project illustrates how Power BI can be leveraged for effective risk management in banking. Through customized dashboards and KPIs, banks can make informed decisions and understand their client base better.

