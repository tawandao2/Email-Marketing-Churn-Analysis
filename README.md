# Email-Marketing-Churn-Analysis
Data analysis project using SQL and Python to identify subscriber churn triggers and retention strategies.

## Executive Summary
Overview
The goal of this analysis was to identify the key factors leading to email unsubscribes and provide data-backed strategies to improve long-term subscriber retention . By analyzing a dataset of 30,000 emails and 1,516 unsubscribes, this report establishes a performance baseline and identifies specific content and behavioral triggers for churn.

## Business Problem 
In a digital landscape where subscriber engagement is increasingly difficult to maintain, businesses face the challenge of "silent disengagement," where users stop opening emails long before they officially unsubscribe. This project analyzes a dataset of 30,000 sent emails to identify the specific triggers—such as campaign category, timing, or privacy concerns that lead to subscriber churn. By establishing a performance baseline and pinpointing underperforming content types, this analysis seeks to propose data-backed retention strategies that stabilize churn rates and optimize the long-term value of an email marketing program.
## Methodology
The analysis followed a structured data pipeline to ensure accuracy and actionable results:

### Data Extraction & Cleaning (SQL)
##### The project began by querying a relational database containing 30,000 email records across five core tables:
Users, Campaigns, Campaign_Performance, Email_Engagement, and Unsubscribes .
##### Metric Calculation:
I used SQL to aggregate total sends and unsubscribes to establish the 5.05% churn baseline.
##### Segmentation: 
I performed joins between campaign and unsubscribe data to calculate specific churn rates for Promotions (5.36%), Announcements (5.27%), Re-engagement (4.87%), and Newsletters (4.82%) .
Behavioral Profiling: SQL was used to identify "At-Risk" users—those with zero opens over their last 5+

### Exploratory Data Analysis (Python)
Using Python in a Google Colab environment, I performed a deeper dive into user behavior:
##### At-Risk Identification:
Filtered the dataset for active users with zero opens over their last 5+ emails to identify segments nearing the churn threshold.

##### Sentiment Analysis:
Categorized the raw feedback from the Unsubscribes table to determine that Privacy concerns (22.03%) was the leading driver of exits.

### Data Visualization & Dashboarding
#### To make the findings accessible for stakeholders, I developed an interactive dashboard using Streamlit and Plotly:
##### Advanced Mapping: 
Implemented a Treemap to visualize the hierarchy of unsubscribe reasons, replacing traditional pie charts for better readability.
##### Categorical Comparison: 
Built dynamic bar charts to highlight that Promotional content churns at a rate 11% higher than Newsletters .

## SQL Analysis Results
#### Analysis Question 1 : What is the overall unsubscribe rate?
This table shows the overall health of the email program, establishing the baseline against which all other metrics are measured.
<img width="314" height="53" alt="image" src="https://github.com/user-attachments/assets/27c77d9e-f4db-4d0f-90a7-b2345a78d1e4" />

This table calculates the program's health by aggregating 30,000 email records to establish a 5.05% churn baseline. By identifying this benchmark, the analysis provides a standard against which all future retention strategies can be measured. It serves as the foundation for the entire project, ensuring that categorical risks are viewed in the proper context of total program performance. 

#### Analysis Question 2: Do certain campaign categories (promotion, newsletter, re-engagement,announcement) have higher unsubscribe rates?
By joining the campaigns and unsubscribes tables, I identified which content types are most likely to drive users away

<img width="771" height="212" alt="image" src="https://github.com/user-attachments/assets/b49e1aeb-c3e3-4ca3-b3a2-e15875d1c07d" />

Using SQL JOIN operations across campaign and engagement tables, this analysis identifies Promotional content as the highest-risk category with a 5.36% churn rate. Contrasting this against the 4.82% rate of Newsletters reveals that sales-heavy content is the primary driver of subscriber loss. This insight allows for a surgical approach to retention, focusing resources on re-evaluating promotional frequency and relevance.

#### Analysis Question 3: How long after signup do users typically unsubscribe?
This data represents the primary reasons users cited for leaving, which informed the strategic recommendations of this project .
<img width="933" height="195" alt="image" src="https://github.com/user-attachments/assets/e92fa07b-8552-4d18-8f50-fe9d89b3b58f" />

This summary quantifies qualitative user feedback to reveal that Privacy concerns (22.03%) and Content Irrelevance (20.12%) are the leading reasons for churn. By transforming raw text reasons into a structured statistical distribution, the analysis shifts the focus from guesswork to addressing specific trust and targeting issues. These findings directly inform the proposed "Privacy-First" and "Segmented Content" strategic pillars.

#### Analysis Question 4: Who are the "at-risk" users?
The following users were identified as "high-risk" due to receiving multiple emails with zero engagement (opens)
<img width="561" height="378" alt="image" src="https://github.com/user-attachments/assets/9eb7d55b-e7c0-466b-8746-b817534d7e6f" />

By filtering for active subscribers with zero opens over 5+ sent emails, this table identifies a high-priority "silent disengagement" segment. It isolates specific User IDs (such as 761 and 4374) who are statistically likely to churn before the average 148-day threshold. Providing these actionable lists allows for immediate intervention through frequency capping or automated win-back flows to prevent permanent subscriber loss.

#### Analysis Question 4: "Which unsubscribe reasons are the most common?"
<img width="511" height="249" alt="image" src="https://github.com/user-attachments/assets/ded097d7-ca31-4708-8a68-360fac0b9462" />

By aggregating qualitative feedback into a structured distribution, this analysis identifies Privacy Concerns (22.03%) and Content Irrelevance (20.12%) as the primary drivers of churn. This technical transition from raw text to statistical insights reveals that subscriber loss is primarily driven by trust and targeting issues rather than email frequency. These findings provide the business with a clear mandate to prioritize data-transparency and content segmentation to protect the existing subscriber base.

 /tmp/ipython-input-2587080778.py:40: FutureWarning:



Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.






 

 
















