Data Cleaning & Preparation | DecodeLabs Internship Project 1

Overview
This project is the first milestone of the Data Analytics internship track at
DecodeLabs. The goal was to take a raw, 1,200-row e-commerce orders dataset and validate, clean, and prepare it to a production-ready ("gold standard") state, proving zero errors on unique identifiers and date formatting before moving on to analysis.

The Dataset
A synthetic e-commerce orders dataset containing 1,200 orders with 14 fields: Order ID, Date, Customer ID, Product, Quantity, Unit Price, Shipping Address, Payment Method, Order Status, Tracking Number, Items In Cart, Coupon Code, Referral Source, and Total Price.

What Was Done

1. Data Validation
Before assuming the data was "already clean," every field was independently checked:
Unique identifiers, verified both `OrderID` and `TrackingNumber` for duplicates using `COUNTIF` based formulas
Date formats checked every date value for validity and confirmed all fall within the expected 2023–2025 range
Missing values audited all 14 columns for blanks using `COUNTBLANK`

2. Findings
| Check | Result |
| Duplicate Order IDs | 0 (0.0%) |
| Duplicate Tracking Numbers | 0 (0.0%) |
| Invalid or incorrectly formatted dates | 0 (0.0%) |
| Missing values | 309 blanks in `CouponCode` only (25.8%) |

The dataset was largely clean on structural integrity, but `CouponCode` had a genuine missing-value issue: 309 orders had no coupon applied, and this was left as a blank cell rather than an explicit value.

3. Cleaning Applied
Blank `CouponCode` values were replaced with the explicit label **"No Coupon"**, so the absence of a coupon is a clear, intentional data point rather than an ambiguous blank
  
Confirmed `TotalPrice` reconciles exactly with `Quantity × UnitPrice` for all 1,200 rows
Standardized the `Date` column to a consistent `YYYY-MM-DD` format

File Structure

DecodeLabs_Project1_DataCleaning.xlsx

Raw Data: original dataset, unmodified
Cleaned Data: cleaned version (formula-linked to Raw Data, not manually retyped)

QA Validation: all validation checks, formulas, and pass/fail results.

Tools Used
Microsoft Excel — `COUNTIF`, `COUNTA`, `COUNTBLANK`, `SUMPRODUCT`, `ISNUMBER`, conditional logic (`IF`)

Key Takeaway
Not every "raw" dataset is messy in the way you expect. Good data cleaning starts with verification, not assumptions, proving a dataset is trustworthy is as important as fixing it when it isn't.

Author: Jonah Victor (JOVIC TECH HUB)
Program: DecodeLabs Data Analytics Internship Project 1

