# EDVIRON_Financial_Overview

This project is based on transaction data from Edviron’s payment platform.
The objective is to understand how revenue is shared between Edviron, ERP partners, and schools, and to analyze settlements and pending exposure.

The entire analysis and dashboard were built using Power BI.

# 2. Data Cleaning

The raw data was not clean, so the following steps were done in Power Query:

Removed unnecessary and empty columns

Handled missing and inconsistent values

Converted all pricing values into actual INR amounts

Standardized pricing fields that were given as Flat or Percentage

Created a Date table for time-based analysis

Only successful transactions were used for revenue calculations.

# 3. Revenue Calculation Logic

Each transaction has three pricing levels:

Edviron Buying Price – Cost paid by Edviron

Partner Pricing – Price charged by Edviron to ERP

Merchant Pricing – Price charged by ERP to schools

Using these values, the revenues were calculated as:

ERP Revenue = Merchant Pricing − Partner Pricing

Edviron Net Revenue = Partner Pricing − Edviron Buying Price

Edviron Gross Revenue = ERP Revenue + Edviron Net Revenue

GMV (Gross Merchandise Value) represents the total transaction amount processed on the platform.

# 4. Data Model

A separate Date table was created and linked to the transaction table.
This allows proper daily and monthly analysis and improves dashboard performance.

All calculations were created using DAX measures, so results update dynamically based on filters.

# 5. Dashboard Design

The dashboard provides a clear financial overview with:

KPI cards showing total transactions, GMV, and revenues

Monthly revenue trend

Revenue split between ERP and Edviron

Gateway-wise and payment-method-wise analysis

Success and failure transaction comparison

Slicers were added for:

Date range

ERP / Institute

Gateway

Payment method

All visuals change automatically when slicers are used.

# 6. Assumptions

Only SUCCESS transactions were considered for revenue

Missing capture status was treated as settled

Pricing values were converted to INR wherever required

These assumptions were used consistently across the analysis.

# 7. Conclusion

This dashboard helps understand revenue performance, partner contribution, and settlement risk.
It provides a simple and clear view for business and finance teams to monitor payment operations.
