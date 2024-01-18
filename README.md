# Understanding CVE Time Lags Between NVD and KEV

This repository contains a Python-based analysis of the duration between when a CVE (Common Vulnerability and Exposure) is published on the National Vulnerability Database (NVD) and when it's added to the Known Exploited Vulnerabilities (KEV) Catalog. It aims to identify trends, patterns, and key factors that influence these time lags.

Key Features
Data Extraction and Cleaning: Acquires data from relevant sources (NVD and KEV) and performs necessary preprocessing and cleaning.
Duration Calculation: Calculates the time difference between NVD publication dates and KEV addition dates for each CVE.
Trend Analysis: Identifies overall trends and patterns in time lags, including potential changes over time.
Cluster Analysis: Groups CVEs based on their time lag characteristics to discover underlying patterns and potential influencing factors.
Top Influencer Identification: Explores factors that might significantly impact time lags, such as CVE severity, vendor responsiveness, or exploit complexity.
Visualizations: Generates informative visualizations to communicate insights effectively, including trend plots, distribution plots, and cluster visualizations.
Project Structure
data/: Contains the raw and processed data files related to CVEs and time lags.
notebooks/: Includes Jupyter Notebooks with detailed code, analysis steps, and results.
images/: Stores generated visualizations to support findings.
README.md (this file): Provides a comprehensive overview of the project.
Dependencies
pandas
numpy
matplotlib
seaborn
scikit-learn (or other clustering libraries, if applicable)
Installation
Clone this repository: git clone https://github.com/your-username/cve_time_lag_analysis.git
Install dependencies: pip install -r requirements.txt
Getting Started
Navigate to the notebooks/ directory.
Open the main notebook (e.g., cve_time_lag_analysis.ipynb) in Jupyter Notebook or a similar environment.
Follow the instructions within the notebook to execute code and explore results.
Contributions and Suggestions
Welcome contributions and suggestions! Please reach out to me on [your preferred communication channel] for further discussions or collaborations.
