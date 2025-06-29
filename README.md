# Glassdoor-Job-Posting-Analysis
A comprehensive data cleaning and exploratory analysis of data science-related job postings *scraped from Glassdoor*.  The goal is to uncover salary trends, hiring patterns, and company insights to help stakeholders make data-driven decisions.

---

## Table of Contents
- [Project Overview](#project-overview)
- [Tools Used](#tools-used)
- [Dataset Overview](#dataset-overview)
- [Data Cleaning Process](#data-cleaning-process)
- [Insights & Findings](#insights--findings)
- [Dashboard](#dashboard)
- [Conclusion](#conclusion)

---
## Project Overview

> "What’s it really like out there for data jobs? Where are the highest salaries? Which roles are booming? And does company size or ownership really matter?"

These were the questions that sparked this project.

In a world where data is driving every decision, the demand for data professionals keeps rising yet the market itself remains surprisingly opaque. Salaries can range from modest to sky-high, job titles vary endlessly, and remote work is reshaping everything.

To bring clarity to this chaos, I scraped real job postings from Glassdoor: over 650+ roles spanning Data Scientist, Analyst, Machine Learning Engineer, and more complete with salary estimates, company ratings, locations, founding years, and ownership types.

But raw data is messy: inconsistent job titles, missing headquarters info, strange salary formats, and placeholder values like “-1” or “\N”.

So I rolled up my sleeves and cleaned it all in *MySQL, carefully standardizing job titles, categorizing ownership types, and grouping remote vs relocated roles. Then, using **Excel*, I visualized the story behind the numbers.

The result?  
A one-page dashboard revealing:
- The most in-demand roles and their average salaries
- How company size and ownership influence pay
- Where remote jobs really come from
- And which states or cities lead in data hiring

For data professionals, this offers a real look into where the opportunities and pay truly are.  
For companies, it’s a glimpse into how they benchmark against the competition.

In the end, it’s all about turning scattered job listings into strategic insights and telling the data story that lives inside.

---
## Tools Used

- *MySQL* – For data cleaning and transformation  
- *Microsoft Excel* – For further cleaning, pivot tables, KPIs and visualizations  
- *GitHub* – For documentation and version control

---

## Dataset Overview

- *Source:* Scraped from [Glassdoor](https://www.kaggle.com/datasets/rashikrahmanpritom/data-science-job-posting-on-glassdoor)
- *Context:* Data science and analytics job listings
- *Size:* ~670+ job postings
- *Key fields:*
  - Job Title
  - Salary Estimate
  - Company Name & Rating
  - Location & Headquarters
  - Company Size, Founded Year
  - Type of Ownership, Industry, Sector

---
## Data Cleaning Process

Main cleaning steps:
- Dropped irrelevant columns: Job Description, Competitors, Revenue
- Removed 'K' from salary columns and converted them to numeric
- Standardized job titles into clean categories (e.g., "Data Scientist", "Machine Learning Engineer")
- Grouped ownership types:
  - “Company - Private” → Private
  - “Company - Public” → Public
  - Others grouped as Nonprofit, Government, Subsidiary, etc.
- Replaced missing values like -1 and \N with Unknown
- Created new column Job Location Type:
  - Remote if location = "Remote"
  - Relocated if location ≠ headquarters
  - On-site if location = headquarters
- **Cleaned the Headquarter column** to enable correct mapping:
  - Removed state codes, keeping only the city (e.g., "New York, NY" → "New York")
  - Standardized countries to include representative cities:
    - "Switzerland" → "Basel, Switzerland"
    - "United Kingdom" → "Cambridge, United Kingdom"
    - "Canada" → "Toronto, Canada"
    - "Japan" → "Tokyo, Japan"
    - "France" → "Paris, France"
    - "Israel" → "Tel Aviv, Israel"
    - "India" → "Bengaluru, India"
    - "Spain" → "Madrid, Spain"
    - "Sweden" → "Stockholm, Sweden"
    - "Bermuda" → "Hamilton, Bermuda"
    - Marked empty headquarters as "Unknown"
  - Removed duplicates and trimmed extra spaces

This cleaning allowed accurate *geographic visualizations* on the map.

---
## Insights & Findings

*KPIs:*
- Total Jobs Posted: ~670+
- Average Company Rating: ~3.7
- Average Salary: $124K/Yr

*Other highlights:*
- Most in-demand roles: Data Scientist, Data Analyst, Data Engineer
- Hiring concentrated in cities like New York, San Francisco, Boston
- Notable share of remote and relocation-friendly roles
- Majority of hiring companies are privately owned

---
## Dashboard

Created in Excel, featuring:
- KPI cards (Total Jobs, Avg Rating, Avg Salary)
- Bar chart: Top Job Posted
- Pie chart: Distribution by ownership type
- Salary range comparison by job title
- Map showing geographic distribution of job postings
- Job location by type

![Glassdoor dashboard](https://github.com/user-attachments/assets/eb6d8edd-8a76-4402-b1e4-6cf5e2a1b0fe)

---
## Conclusion

The analysis:
- Reveals salary benchmarks and hiring trends for data science jobs
- Shows where most opportunities are (cities & companies)
- Helps stakeholders plan recruitment and helps job seekers target high-demand roles

> Dataset scraped from Glassdoor. This project is for educational and analysis purposes only.







