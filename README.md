# AWS-Portfolio

# Business Licensing Data Analytics on AWS

This project is part of my MBA coursework in **Cloud Computing** and demonstrates my ability to use Amazon Web Services (AWS) to perform a full **Descriptive Analysis** on business licensing data from the **City of Vancouver**.

This is my **first cloud project** and my **first GitHub portfolio**, and it showcases my journey as I begin building practical cloud solutions using AWS.

---

## Project Objective

To analyze business licensing data for the City of Vancouver (1997–2012) using AWS cloud services and uncover patterns in license issuance and fee collection. The analysis includes multiple phases: data ingestion, profiling, cleaning, cataloging, summarization, and visualization.

---

## Dataset Information

- **Source:** [City of Vancouver Open Data Portal](https://opendata.vancouver.ca/)
- **Dataset Name:** `business-licences-1997-to-2012`
- **Formats Used:** CSV and JSON
- **Folder:** [`datasets/`](./datasets/)

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

The project is organized into **five key phases**, each stored in its own folder with screenshots and explanations.

| Phase | Folder | Description |
|-------|--------|-------------|
| **Phase 1** | [`phase-1-ingestion/`](./phase-1-ingestion) | Uploading dataset to S3, enabling encryption, versioning, and replication |
| **Phase 2** | [`phase-2-profiling/`](./phase-2-profiling) | Profiling the raw data using AWS Glue DataBrew |
| **Phase 3** | [`phase-3-cleaning/`](./phase-3-cleaning) | Cleaning and transforming using DataBrew recipes |
| **Phase 4** | [`phase-4-cataloging/`](./phase-4-cataloging) | Cataloging structured data using Glue Crawlers |
| **Phase 5** | [`phase-5-summarization/`](./phase-5-summarization) | Summarizing and querying using Glue Studio and Athena |

---

## Visualizations

Visual charts that show trends in business licensing activities:
- Issuance volume across years
- Monthly fee trends  
See: [`visualizations/`](./visualizations/)

---

## Certification

I have earned the **AWS Cloud Practitioner (Foundations)** certification, which demonstrates my understanding of AWS Cloud concepts, services, and basic architectural best practices.

📌 Certification Image: [`certification/aws-cloud-practitioner.png`](./certification/aws-cloud-practitioner.png)

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

