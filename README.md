# 🏥 Raleigh Hospital Price Transparency Analysis

## 📋 Project Overview

This project evaluates whether publicly available hospital pricing data provides meaningful transparency and supports reliable price comparisons across healthcare organizations.

The analysis combines pricing files from five Raleigh area hospitals and examines reporting completeness, procedure code standardization, pricing field availability, and published price variation.

The project uses Python for data preparation, SQL Server for validation and analysis, and Power BI for interactive reporting and data exploration.

## 📸 Dashboard Preview

![Hospital Price Transparency Dashboard](https://github.com/sheel93807/Hospital-Price-Transparency-Data-Project/blob/main/HospitalPriceTransparencyDataProjectScreenshot.png)

## 🎯 Project Objective

Evaluate pricing transparency across five Raleigh area hospitals by examining reporting quality, standardizing procedure codes, and comparing published prices for similar services.

## 🏨 Hospitals Included

* Duke Raleigh Hospital
* UNC Rex Healthcare
* WakeMed Raleigh Campus
* WakeMed Mental Health & Well Being Hospital
* Holly Hill Hospital

## 🛠️ Tools and Technologies

* 🐍 Python
* 🐼 Pandas
* 🔢 NumPy
* 🗃️ SQL
* 🖥️ SQL Server
* ⚙️ SQL Server Management Studio
* 📊 Power BI
* 🔄 Power Query
* 📐 DAX

## 📁 Dataset Overview

* 📄 718,778 standardized pricing records
* 🏥 5 Raleigh area hospitals
* 📋 16 standardized columns
* 🔗 640 comparable MS DRG procedures reported by at least three hospitals
* 3️⃣ 627 MS DRG procedures reported by three hospitals
* 4️⃣ 13 MS DRG procedures reported by four hospitals

The original files used different reporting structures. Duke Raleigh Hospital, WakeMed Raleigh Campus, WakeMed Mental Health & Well Being Hospital, and UNC Rex Healthcare used wide pricing formats with metadata and header differences. Holly Hill Hospital used a long payer level format.

## 🌐 Data Source

Hospital pricing files were obtained from the [Hospital Price Files Finder](https://hospitalpricingfiles.org/).

> “Find machine readable and user friendly price transparency files for all hospitals.”

## 🔄 Project Workflow

### 1️⃣ Hospital Pricing Files

Collected publicly available machine readable hospital pricing files from the Hospital Price Files Finder.

### 2️⃣ Python Data Preparation

Used Python and Pandas to:

* 🔍 Inspect source file structures
* 🧹 Remove metadata and invalid header rows
* 📝 Standardize column names
* 🏷️ Clean procedure codes and descriptions
* 🔢 Convert pricing fields to numeric values
* ❓ Address missing values
* ✅ Validate record counts
* 💳 Preserve meaningful payer level records
* 🔗 Combine the cleaned files into one standardized dataset

### 3️⃣ SQL Server Analysis

Used SQL Server to:

* ✅ Validate the combined dataset
* 📋 Review reporting completeness
* 📊 Analyze procedure code distributions
* 🔄 Normalize MS DRG codes
* 🔗 Identify shared procedures
* 💰 Compare matching hospital prices
* ➗ Calculate gross charge differences
* 🗃️ Create analysis views for Power BI

### 4️⃣ Power BI Reporting

Developed a six page interactive report containing:

1. 📊 Executive Overview
2. ✅ Reporting Completeness and Data Availability
3. 💰 Comparable MS DRG Pricing Analysis
4. 🔎 MS DRG Procedure Price Explorer
5. 📈 MS DRG Gross Charge Difference Analysis
6. 📚 Methodology, Definitions, and Limitations

## 🗃️ SQL Views

The SQL analysis includes the following views:

### `vw_normalized_drg_prices`

Standardizes MS DRG codes and prepares procedure pricing records for comparison.

### `vw_shared_drg_comparison`

Identifies MS DRG procedures reported by at least three hospitals.

### `vw_drg_hospital_comparison`

Supports hospital level procedure exploration in Power BI.

### `vw_duke_unc_drg_comparison`

Places Duke Raleigh and UNC Rex gross charges on the same row, calculates the absolute difference, and identifies the hospital with the higher published gross charge.

## 📊 Dashboard Pages

### 🏥 Executive Overview

Introduces the dataset through:

* Published pricing records by hospital
* Procedure code distribution
* Comparable MS DRG count
* Project objective
* Key dataset findings

### ✅ Reporting Completeness and Data Availability

Evaluates the percentage of records containing:

* Gross charges
* Cash charges
* Minimum negotiated charges
* Maximum negotiated charges

This page also compares procedure code composition across hospitals.

### 💰 Comparable MS DRG Pricing Analysis

Compares Duke Raleigh Hospital and UNC Rex Healthcare across 636 matching MS DRG procedures.

The page includes:

* Average gross charge
* Average cash charge
* Average cash discount
* Lower gross price comparison
* Lower cash price comparison

### 🔎 MS DRG Procedure Price Explorer

Allows users to select:

* Hospital
* MS DRG code
* Procedure description

The page displays available gross, cash, minimum, and maximum charges for the selected procedure. Missing pricing fields are clearly identified as not reported.

### 📈 MS DRG Gross Charge Difference Analysis

Ranks the twenty matching MS DRG procedures with the largest published gross charge differences between Duke Raleigh Hospital and UNC Rex Healthcare.

### 📚 Methodology, Definitions, and Limitations

Documents:

* Project workflow
* Analytical decisions
* Important pricing definitions
* Reporting limitations
* Project conclusions

## 🔑 Key Findings

* 🏥 Duke Raleigh Hospital contributed 57.66 percent of the combined pricing records.

* 📋 Revenue Codes and Chargemaster Codes accounted for more than 94 percent of all records.

* 🔗 The analysis identified 640 comparable MS DRG procedures reported by at least three hospitals.

* 🤝 Duke Raleigh Hospital and UNC Rex Healthcare shared 636 matching MS DRG procedures with comparable gross and cash pricing fields.

* 📉 UNC Rex Healthcare reported the lower gross charge for 55.82 percent of the 636 matching procedures.

* 💵 Duke Raleigh Hospital reported the lower cash price for 94.34 percent of matching procedures.

* 🏷️ Duke Raleigh Hospital had an average cash discount of approximately 73 percent, compared with approximately 40 percent at UNC Rex Healthcare.

* 💲 The average published cash charge at Duke Raleigh Hospital was approximately $21,372 lower than the average published cash charge at UNC Rex Healthcare.

* ⚠️ The largest gross charge difference for a matching MS DRG procedure exceeded $432,000.

* 🚫 Holly Hill Hospital reported Revenue Codes rather than comparable MS DRG procedures and could not participate in the MS DRG pricing comparison.

* ❓ Some hospitals reported the same MS DRG procedures without providing the same pricing fields, limiting direct comparisons.

## 🧾 Project Conclusion

This project found that public access to hospital pricing files does not automatically create meaningful transparency.

Differences in file structure, coding systems, pricing field availability, and reporting completeness required extensive preparation before reliable comparisons could be performed.

Patients ultimately benefit from improved healthcare price transparency, but healthcare organizations, researchers, and regulators are in the strongest position to improve reporting quality.

Additional reporting requirements, standardized file submissions, consistent procedure identifiers, complete pricing fields, and stronger accountability for inadequate submissions could make hospital pricing data more accurate, comparable, and useful.

Publishing pricing files is only the first step. Meaningful transparency requires information that is complete, standardized, accessible, and understandable.

## ⚠️ Important Limitations

* Published hospital prices may differ from what a patient ultimately pays because insurance coverage, negotiated benefits, deductibles, facility fees, and additional services can affect final costs.

* Hospitals used different reporting structures, pricing methodologies, and coding systems.

* Not every hospital reported every pricing field for each procedure.

* Gross and cash comparisons were limited to hospitals with available values for those fields.

* Record counts represent published pricing records, not patient visits or unique services.

* The analysis evaluates published prices and reporting quality. It does not estimate final patient responsibility.
