# Understanding CVE Time Lags Between NVD and KEV
<p align="justify">
This repository contains a Python-based analysis of the duration between when a CVE (Common Vulnerability and Exposure) is published on the National Vulnerability Database (NVD) and when it's added to the Known Exploited Vulnerabilities (KEV) Catalog. It aims to identify trends, patterns, and key factors that influence these time lags.
</p>
<br>
<strong>Key Features</strong>
<br>
<br>
<p align="justify">
Data Extraction and Cleaning: Acquires data from relevant sources (NVD and KEV) and performs necessary preprocessing and cleaning.
<br>
Duration Calculation: Calculates the time difference between NVD publication dates and KEV addition dates for each CVE.
<br>
Trend Analysis: Identifies overall trends and patterns in duration from CVE to KEV, including potential changes over time.
<br>
Cluster Analysis: Groups CVEs based on common characteristics to discover potential influencing factors.
<br>
Top Influencer Identification: Explores factors that might significantly impact the duration, such as CVE severity, vendor responsiveness etc.
<br>
Visualizations: Generates informative visualizations including trend plot, distribution plot, and cluster visualization.
</p>
<br>
<strong>Project Structure</strong>
<p align="justify">
Summary Article: <a href="https://github.com/yamineesh-k/cve_kev_duration/blob/main/cvetokevsummary.md">CVE to KVE Summary</a>
<br>
data/: Contains the rocessed data files related to CVEs and Clusters.
<br>
notebooks/: Includes Jupyter Notebooks with detailed code, analysis steps, and results.
<br>
images/: Stores generated visualizations to support findings.
<br>
README.md (this file): Provides a comprehensive overview of the project.
<br>
Dependencies: pandas, numpy, matplotlib, seaborn, scikit-learn
<br>
</p>
<strong>Installation</strong>
<p align="justify">
<br>
Clone this repository: git clone https://github.com/your-username/cve_kev_duration.git
<br>
Install dependencies: pip install -r requirements.txt
<br>
</p>
<strong>Getting Started</strong>
<br>
Navigate to the notebooks/ directory.
<br>
Open the main notebook (cve_nvd_to_kev_analysis.ipynb) in Jupyter Notebook or a similar environment.
<br>
Follow the instructions within the notebook to execute code and explore results.
<br>
<br>
<strong>Contributions and Suggestions</strong>
Welcome contributions and suggestions! Please reach out to me at https://www.linkedin.com/in/yamineesh/ for further discussions or collaborations.
