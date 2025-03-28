# AWS-Portfolio

# Business Licensing Data Analytics on AWS

This project is part of my MBA coursework in **Cloud Computing** and demonstrates my ability to use Amazon Web Services (AWS) to perform a full **Descriptive Analysis** on business licensing data from the **City of Vancouver**.

This is my **first cloud project** and my **first GitHub portfolio**, and it showcases my journey as I begin building practical cloud solutions using AWS.

---

## Project Objective

To analyze business licensing data for the City of Vancouver (1997–2012) using AWS cloud services and uncover patterns in license issuance and fee collection. The analysis includes multiple phases: data ingestion, profiling, cleaning, cataloging & summarization, analysis, and governance & monitoring.


---

## Dataset Information: Business Licences 1997–2012

The dataset includes business licence records from **1997 to 2012**, collected by the **City of Vancouver** under Licence By-Law No. 4450. It captures details about licensing, business types, and locations within the city. The dataset is available in both **CSV** and **JSON** formats and includes the following key features:

- **LicenceRSN:** A unique identifier for each business licence issued  
- **LicenceNumber:** Encoded with year and system-generated number (e.g., `97-144521`)  
- **BusinessName:** Official name or ownership of the business  
- **BusinessTradeName:** Name under which the business typically operates  
- **Status:** Indicates licence state (e.g., *Issued*, *Cancelled*, *Gone Out of Business*)  
- **IssuedDate / ExpiredDate:** Start and end dates of the licence validity  
- **BusinessType:** Type of business activity (e.g., *Health Services*, *Retail Dealer*)  
- **BusinessSubType:** Further classification under the main type (e.g., *Tanning Salon*)  
- **Street Address Fields:** Includes `Unit`, `House`, `Street`, `City`, `Province`, `Country`, and `PostalCode`  
- **LocalArea:** Planning zone within Vancouver (e.g., *Fairview*, *Downtown*)  
- **NumberofEmployees:** Reported number of employees
- **FeePaid:** Licensing fee paid in Canadian dollars  
- **ExtractDate:** When the data was exported from the City's database  

This dataset is used throughout the project for ingestion, profiling, cleaning, and summarization tasks in AWS.


- **Source:** [City of Vancouver Open Data Portal](https://opendata.vancouver.ca/)
- **Dataset Name:** `business-licences-1997-to-2012`
- **Formats Used:** CSV and JSON
- **Folder:** [`datasets/`](./datasets/)

---

## Methodology: AWS-Based Descriptive Analytics Workflow

This methodology adapts the professor’s recommended process to a cloud-native AWS workflow.

### 1. Data Collection and Preparation
- Uploaded dataset to **Amazon S3** using **EC2**
- Set up encryption (KMS), versioning, and replication

### 2. Data Profiling
- Used **AWS Glue DataBrew** to analyze:
  - Missing values
  - Column distributions
  - Summary statistics

### 3. Data Cleaning
- Applied cleaning recipes in DataBrew:
  - Removed unnecessary columns
  - Filled missing values
  - Converted to Parquet format for optimization

### 4. Data Cataloging
- Created **AWS Glue Crawlers** to register structured schema in **AWS Glue Data Catalog**

### 5. Data Summarization
- Built an ETL pipeline in **Glue Studio**
- Used **Amazon Athena** to query and summarize trends
- Output stored in a final “transfer” S3 bucket

### Insights and Learnings

The descriptive analysis conducted on the business licensing dataset from the City of Vancouver (1997–2012) provided critical insights into patterns in license issuance and associated fees.

From the trend chart, we observed consistent activity from 2002 to 2009, with peak total fees collected in **2007 (≈ $24,146)** and **2004–2008** showing sustained high revenue from licensing. The number of licenses issued also followed this trend, with counts generally ranging from **30–40 licenses per year** during that period. A notable decline in both the number of licenses and fees occurred after 2009, with the lowest activity in 2012.

The top five business types in this dataset were:
- **Live-aboards** (128 instances)
- **One-Family Dwelling** (58)
- **Office** (39)
- **Duplex** (34)
- **Multiple Dwelling** (28)

This suggests a strong presence of home-based or residential business licensing during this period, particularly before changes made in 2018 that limited the disclosure of address data for home-based businesses.

Fee distribution also indicated a significant range, with some years collecting upwards of **$23,000+ CAD**, while others (especially post-2010) showed a sharp decline. Profiling also revealed that a majority of businesses either reported **zero employees or left the field as '000'**, reflecting potential data entry inconsistency or a high volume of sole proprietorships.

This analysis not only helped identify key licensing trends and revenue patterns but also demonstrated the value of structuring raw open data into optimized formats for deeper insight generation.

---

### Recommendations

Based on the descriptive analysis, the following recommendations can be proposed:

1. **Improve Employee Data Consistency**  
   The `NumberofEmployees` field is often reported as `0` or `000`, which likely masks the true business scale. Introducing dropdown-based data entry or enforced validations (e.g., numeric range only) during licensing applications could improve data reliability.

2. **Focus Monitoring on Peak Activity Windows**  
   The years between **2002–2009** demonstrated the highest business activity and revenue generation. City administrators should analyze policy or economic factors from that period to understand what facilitated higher engagement.

3. **Enhance Business Type Classification**  
   Categories such as *Live-aboards* or *One-Family Dwelling* appeared frequently and may require modern restructuring or merging under updated classification codes. Streamlining these can support better longitudinal comparisons.

4. **Automate Data Governance Pipelines**  
   While this project used AWS Glue and Athena for post-hoc processing, a future pipeline that regularly syncs, validates, and profiles licensing data in near real-time could enhance transparency and operational efficiency for city departments.

---

##  AWS Services Used

| Service           | Purpose                                                                 |
|------------------|-------------------------------------------------------------------------|
| **Amazon EC2**    | Upload and prepare dataset for S3                                       |
| **Amazon S3**     | Store raw, cleaned, and transformed datasets                            |
| **AWS Glue DataBrew** | Profiling, cleaning, and transformation                              |
| **AWS Glue Crawler** | Create and manage AWS Glue Data Catalog                              |
| **AWS Glue Studio**  | Visual ETL pipelines for summarization                               |
| **Amazon Athena**    | SQL-based analysis and summarization                                 |
| **AWS CloudWatch**   | Monitoring logs and job performance                                  |
| **AWS CloudTrail**   | Track access and configuration history                               |
| **AWS KMS**          | Encryption using customer-managed keys                               |

---

## Project Architecture

![Data Analytics Platform Diagram](architecture/dap-workflow.png)

This architecture showcases how the dataset moves from ingestion to summarization across AWS services, with encryption, versioning, and monitoring enabled for governance.

---

## Project Workflow

The project is organized into **six key phases**, each stored in its own folder with screenshots and explanations.

| Phase | Folder | Description |
|-------|--------|-------------|
| **Phase 1** | [`phase-1-ingestion/`](./phase-1-ingestion) | Uploading dataset to S3, enabling encryption, versioning, and replication |
| **Phase 2** | [`phase-2-profiling/`](./phase-2-profiling) | Profiling the raw data using AWS Glue DataBrew |
| **Phase 3** | [`phase-3-cleaning/`](./phase-3-cleaning) | Cleaning and transforming using DataBrew recipes |
| **Phase 4** | [`phase-4-cataloging/`](./phase-4-cataloging) | Cataloging structured data using Glue Crawlers |
| **Phase 5** | [`phase-5-summarization/`](./phase-5-summarization) | Summarizing and querying using Glue Studio and Athena |

---

##  Interactive Visualization (City of Vancouver Portal)

The chart below shows licensing fee trends over time based on the dataset used in this project.

[View Interactive Chart on City of Vancouver Portal](https://opendata.vancouver.ca/explore/dataset/business-licences-1997-to-2012/analyze/?disjunctive.businesssubtype&disjunctive.status&refine.city=VANCOUVER&dataChart=eyJxdWVyaWVzIjpbeyJjaGFydHMiOlt7ImFsaWduTW9udGgiOnRydWUsInR5cGUiOiJsaW5lIiwiZnVuYyI6IkNPVU5UIiwieUF4aXMiOiJmZWVwYWlkIiwic2NpZW50aWZpY0Rpc3BsYXkiOnRydWUsImNvbG9yIjoiIzYxYTY0NCJ9LHsidHlwZSI6ImxpbmUiLCJmdW5jIjoiU1VNIiwieUF4aXMiOiJmZWVwYWlkIiwic2NpZW50aWZpY0Rpc3BsYXkiOnRydWUsImNvbG9yIjoiIzAyNzlCMSJ9XSwieEF4aXMiOiJpc3N1ZWRkYXRlIiwibWF4cG9pbnRzIjpudWxsLCJ0aW1lc2NhbGUiOiJtb250aCIsInNvcnQiOiIiLCJzZXJpZXNCcmVha2Rvd25UaW1lc2NhbGUiOiIiLCJjb25maWciOnsiZGF0YXNldCI6ImJ1c2luZXNzLWxpY2VuY2VzLTE5OTctdG8tMjAxMiIsIm9wdGlvbnMiOnsiZGlzanVuY3RpdmUuYnVzaW5lc3NzdWJ0eXBlIjp0cnVlLCJkaXNqdW5jdGl2ZS5zdGF0dXMiOnRydWUsInJlZmluZS5jaXR5IjoiVkFOQ09VVkVSIn19fV0sImRpc3BsYXlMZWdlbmQiOnRydWUsImFsaWduTW9udGgiOnRydWUsInRpbWVzY2FsZSI6IiJ9)

---

## Certification

I have earned the **AWS Cloud Practitioner (Foundations)** certification, which demonstrates my understanding of AWS Cloud concepts, services, and basic architectural best practices.

📌 Certification: [View Certification PDF](certification/AWS-Cloud-Foundations-certificate-Ashwani.pdf)

![AWS Cloud Foundations Badge](certification/aws-cloud-foundations-badge-ashwani.png)


---

## GitHub Pages Portfolio

🔗 View my public portfolio site: [https://buildwithashwani.github.io/AWS-Portfolio](https://buildwithashwani.github.io/AWS-Portfolio)

This portfolio showcases all five phases visually and interactively using HTML and GitHub Pages.

---

## Key Learnings & Outcome

- Gained hands-on experience with the **AWS Analytics ecosystem**
- Successfully processed and transformed real-world open data
- Improved understanding of data profiling, governance, and security
- Designed scalable cloud-based data analytics workflows

---

## About Me

👋 I'm **Ashwani**, an MBA student with a background in architecture and a growing passion for cloud computing and analytics.  
This project marks the start of my journey in building real-world AWS solutions.

---

