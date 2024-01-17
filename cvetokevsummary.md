# CVE - From Discovery to Exploit
 _Assessing the Time Duration Between Vulnerability Disclosure and Knowledge Base Integration_

**INTRODUCTION**

<p align="justify">
Delving into process lifecycles and understanding the forces shaping each stage is always interesting. This article explores the journey of Common Vulnerabilities and Exposures (CVEs) from the National Vulnerability Database (NVD) to Known Exploited Vulnerabilities (KEV), focusing on the time it takes for this transition – a metric referred to as 'DaystoKEV', in this article. Though both NVD and CISA have different analysis goals, the journey of a CVE from NVD to KEV looks the below, at a High Level. Steps 3,4 and 5 are independent processes and need not happen in sequence.
</p>
<p align="center">
<img width="480" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/1d7c084e-802b-4555-be0a-48dfb45bc5a9">
</p>
<strong>CALCULATING DAYS TO KEV</strong>
<br>
<br>
<p align="justify">
To calculate the 'DaystoKEV', the NVD CVE Data and KEV Data were merged. The difference between 'Published' date from the CVE data and 'Date Added' from the KEV data was calculated (in days). The distribution of 'DaystoKev', as visualized below is skewed to the right, suggesting that a majority of KEVs have lower values (relatively), with peak around 0-1000 days. There is also huge variability in the values with a wide range. With this foundational undersstanding, Let's explore further.
</p>
<p align="center">
<img width="400" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/d0379b0b-b21d-4019-93f2-18aaa6639ac4">
</p>
<strong>TREND ANALYSIS</strong>
<br>
<br>
<p align="justify">
When the average 'DaystoKEV' and 'Number of KEVs' were visualized by month, we can see a 'downward' trend in both the metrics. However, we should note that the KEV data only started in Nov-21 and the initial weeks had a significant backlog of CVEs added that strongly influenced the high values. The downward trend is also reflective of faster exploitation of published vulnerabilities. As of writing this analysis (15th Jan 2024), we already have a KEV added for a CVE (CVE-2024-21887, Vendor: Ivanti) published in 2024, which is reflective of the faster exploitation duration.
</p>
<p align="center">
<img width="590" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/503193e5-59d1-4c74-8b15-c21428dc0989">
</p>
<p align="justify">
When the specific duration for each KEV was visualized as a scatter plot (below), with the top vendors (the KEVs are assigned to) colored different, we see a wider distribution. Notice the Green markers (Microsoft) clutterred in Mid-2022. We also notice that there are KEVs with Negative 'DaystoKev'. There are 50 such KEVs. This is because the KEV catalog specifically focuses on vulnerabilities with known exploits. So it may list CVEs that are actively being exploited even if they haven't yet been fully analyzed and published on the NVD. The KEV criteria followed by CISA are explained <a href="https://www.cisa.gov/known-exploited-vulnerabilities">here</a> in detail. There are also 42 KEVs which were added on the same day they were Published on NVD due to similar reasons.
</p>
<p align="center">
<img width="590" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/fb0e5701-dd52-4c71-bd57-804609ff7799">
</p>
<p align="justify">
Do CVEs with higher Base Score make it to KEV faster than the ones with low scores? To answer this, let's look at the correlation plot of the 'Base Score' assigned by NVD and the 'DaystoKEV'. The points are scattered across the plot, forming a curved pattern rather than a straight line. The relation is not linear. We can also observe that 'daystokev' tends to increase as 'BaseScore' decreases.
</p>
<p align="center">
<img width="400" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/06e93233-24b2-443d-a55e-b6370de32579">
</p>
<strong>CLUSTER ANALYSIS</strong>
<br>
<br>
<p align="justify">
To identify clusters (groups of observations with similar characteristics), three factors were used - 'Vendor', 'DaystoKEV' and 'BaseScore'. These factors were chosen based on the intution built from the exploration thus far but can be modified per requirement. Before running a clustering algorithm like K-means, to determine the 'K', elbow plot was used to determine the optimal K value. Optimal K guides us to a clustering solution that balances tightness within clusters and separation between them.
</p>
<p align="center">
<img width="450" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/c4a87a3d-53b2-4fbd-8cab-483294021990">
</p>
<p align="justify">
There were 5 distinct clusters observed from the KEV data. When visualized on a 3D space, here is how they would look. The clear distinction between these groups can be seen here. We also should manually explore the clusters formed to define their dominant characteristics.
</p>
<p align="center">
<img width="420" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/78cdb056-5c54-47e1-83d1-054855b155d3">
</p>
<p align="justify">
<strong>Cluster 1</strong>: A group of 165 KEVs, assigned preodominantly to Microsoft and Adobe, with low base score and not majorly assigned to Known Ransomware attacks. These took a while to be published (Median: 3224 days). Pre 2021 backlogs with Low risk.
</p>
<p align="justify">
<strong>Cluster 2</strong>: A group of 292 KEVs, assigned to Microsoft and Google, with base scores between 7-8 and moderately assigned to Known Ransomware attacks. These took relatively lesser duration to be published (Median: 266 days). Moderate Risk Cluster.
</p>
<p align="justify">
<strong>Cluster 3</strong>: A group of 162 KEVs, dominantly Microsoft, with base scores between 8-9 and highly assigned to Known Ransomware attacks. These took longer to be added (Median: 1690 days). Old High Risk Microsoft Cluster.
</p>
<p align="justify">
<strong>Cluster 4</strong>: A group of 289 KEVs, mostly Apple and Cisco, with base scores between >= 8.8 and not frequently assigned to Known Ransomware attacks. These took relatively moderate duration to be added (Median: 892 days). Low to Moderate Risk Cluster.
</p>
<p align="justify">
<strong>Cluster 5</strong>: A group of 160 KEVs, consolidates other vendors (VMWare, Samsung and TrendMicro leading), base scores between >= 8.8 and moderately frequent is assignment to Known Ransomware attacks. These took relatively lesser duration to be added (Median: 376 days). Moderate Risk Cluster.
</p>
</p>
<strong>HIGH INFLUENCE FACTORS</strong>
<br>
<br>
<p align="justify">
In this last section, the focus is on investigating if a 'vendor' or the 'month' when a CVE is published has any influence on the 'DaystoKEV'. An ordinary least squares (OLS) linear regression model was used to fit this theory. 
</p>
<p align="center">
<img width="400" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/006aa12e-ebba-4a60-bb57-cd41aaece0c3">
</p>
<br>
<p align="justify">
While the model only moderately explains the variance in 'DaystoKEV', indicating other features need to be included, there were some significant factors and interactions that were identified in driving the 'DaystoKev' to be longer. The strongest of these factors from a Vendor (with atleast 10 KEVs) factor are Adobe, Oracle and Linux. The same vendor in a different order- Oracle, Adobe and Linux have strong influence of the calendar month, meaning, if a CVE is published later in the year, it is likely to take relatively longer to be added to the KEV than the start of the year.  
<br>
It is important to recognize that meaningful insights often emerge from constantly exploring diverse angles and interpretations of the data.
</p>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p align="center">
*** <em>End of Report</em> ***  
</p>
