# AWS Immigration Data Pipeline & Power BI Analysis

## Project Overview
This project demonstrates an end-to-end data analytics pipeline using AWS S3, Python, and Power BI. 
The goal is to simulate a real-world analytics workflow where raw data is stored in cloud storage, 
processed programmatically, and consumed by a BI tool for visualization and insights.

The project uses U.S. immigration data to showcase cloud-based data handling, preprocessing, 
and dashboard creation.

---

## Architecture Overview
**Flow:**
Local Machine → AWS S3 (Raw Data) → Python Processing → AWS S3 (Processed Data) → Power BI

- Raw immigration data is uploaded to AWS S3
- Python is used to read, clean, and preprocess data from S3
- Cleaned data is uploaded back to S3 programmatically
- Power BI connects to the processed data using an S3 presigned URL

---

## Dataset
- **Source:** Public U.S. immigration datasets
- **Data Type:** CSV (aggregated immigration and enforcement statistics)
- **Storage:** AWS S3
- **Handling:**
  - Raw data uploaded manually to S3
  - Processed data uploaded programmatically using Python

Due to dataset size considerations, raw and processed CSV files are not stored directly in this repository.

---

## Tools & Technologies
- **AWS S3**
  - Cloud storage for raw and processed datasets
- **Python**
  - Data cleaning and preprocessing
  - AWS SDK (`boto3`) for S3 interaction
- **Power BI**
  - Data ingestion via presigned S3 URL
  - Interactive dashboards and visual analysis

---

## Data Processing (Python)
- Configured AWS access locally using `aws configure`
- Read raw CSV data directly from AWS S3
- Cleaned and transformed data:
  - Removed inconsistencies
  - Handled missing values
  - Standardized columns
- Uploaded processed data back to AWS S3 programmatically

> Note: AWS credentials are **not hardcoded** and are not included in this repository.

---

## Power BI Integration
- Generated a presigned URL for the processed dataset stored in S3
- Connected Power BI to the dataset using **Web** data source
- Built dashboards to analyze immigration trends and enforcement metrics

---

## Key Insights
- Immigration trends show long-term stability in lawful permanent residents with periodic fluctuations.
- Refugee arrivals vary significantly across years, reflecting sensitivity to policy and global events.
- Enforcement-related metrics show cyclical patterns over time.
- Cloud-based storage enables scalable and repeatable analytics workflows.

---

## Dashboard Preview

### AWS-Based Immigration Overview
![AWS Immigration Dashboard](images/aws_immigration_overview_dashboard.png)

### Immigration Trends Analysis
![Immigration Trends Dashboard](images/aws_immigration_trends_dashboard.png)

---

## Repository Structure
```text
aws-immigration-data-pipeline-powerbi/
│
├── notebooks/
│   └── immigration_s3_data_pipeline.ipynb
│
├── data/
│   ├── raw/
│   ├── processed/
│   
│
├── images/
│
├── powerbi/
│   └── aws_immigration_dashboard.pbix
│
└── README.md
```

Future Enhancements
- Store processed data in AWS RDS (PostgreSQL)
- Replace presigned URL ingestion with direct database connection
- Extend analysis using SQL-based transformations
- Automate the pipeline using scheduled workflows

Disclaimer

This project is for educational and portfolio purposes only and does not represent official government analysis or policy recommendations.

