# CVE - From Discovery to Exploit
 _Assessing the Time Duration Between Vulnerability Disclosure and Knowledge Base Integration_

**INTRODUCTION**

<p align="justify">
Delving into process lifecycles and understanding the forces shaping each stage is always interesting. This article explores the journey of Common Vulnerabilities and Exposures (CVEs) from the National Vulnerability Database (NVD) to Known Exploited Vulnerabilities (KEV), focusing on the time it takes for this transition – a metric referred to as 'DaystoKEV', in this article. Though both NVD and CISA have different analysis goals, here is how the journey of a CVE from NVD to KEV looks, at a High Level. Step 3 and Step 5 are independent processes and need not happen in sequence.
</p>
<br>
<p align="center">
<img width="480" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/1d7c084e-802b-4555-be0a-48dfb45bc5a9">
</p>
<br>
<strong>CALCULATING DAYS TO KEV</strong>
<br>
<br>
<p align="justify">
To calculate the 'DaystoKEV', the NVD CVE Data and KEV Data were merged. The difference between 'Published' date from the CVE data and 'Date Added' from the KEV data was calculated (in days). The distribution of 'DaystoKev', as visualized below is skewed to the right, suggesting that a majority of KEVs have lower values (relatively), with peak around 0-1000 days. There is also huge variability in the values with a wide range. With this foundational undersstanding, Let's explore further.
</p>
<br>
<p align="center">
<img width="400" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/d0379b0b-b21d-4019-93f2-18aaa6639ac4">
</p>
<br>
<strong>TREND ANALYSIS</strong>
<br>
<br>
<p align="justify">
When the average 'DaystoKEV' and 'Number of KEVs' were visualized by month, we can see a 'downward' trend in both the metrics. However, we should note that the KEV data only started in Nov-21 and the initial weeks had a significant backlog of CVEs added that strongly influenced the high values. The downward trend is also reflective of faster exploitation of published vulnerabilities. As of writing this analysis (15th Jan 2024), we already have a KEV added for a CVE (CVE-2024-21887, Vendor: Ivanti) published in 2024, which is reflective of the faster exploitation duration.
</p>
<br>
<p align="center">
<img width="550" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/af5b63ed-037f-4661-ab3e-1656184542f4">
</p>
<p align="justify">
When the specific duration for each KEV was visualized as a scatter plot (below), with the top vendors (the KEVs are assigned to) colored different, we see a wider distribution. Notice the Green markers (Microsoft) clutterred in Mid-2022. We also notice that there are KEVs with Negative 'DaystoKev'. There are 50 such KEVs. This is because the KEV catalog specifically focuses on vulnerabilities with known exploits. So it may list CVEs that are actively being exploited even if they haven't yet been fully analyzed and published on the NVD. The KEV criteria followed by CISA are explained <a href="https://www.cisa.gov/known-exploited-vulnerabilities">here</a> in detail. There are also 42 KEVs which were added on the same day they were Published on NVD due to similar reasons.
</p>
<br>
<p align="center">
<img width="590" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/fb0e5701-dd52-4c71-bd57-804609ff7799">
</p>
<br>
<p align="justify">
Do CVEs with higher Base Score make it to KEV faster than the ones with low scores? To answer this, let's look at the correlation plot. The points are scattered across the plot, forming a curved pattern rather than a straight line. The overall pattern of the points is curved, not straight. A straight line to represent the correlation results in a poor fit, and yet we can observe that 'daystokev' tends to increase as 'BaseScore' decreases.
</p>
<p align="center">
<img width="450" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/06e93233-24b2-443d-a55e-b6370de32579">
</p>
<br>
<strong>CLUSTER ANALYSIS</strong>
<br>
<br>
<p align="justify">
To identify clusters or groups with similar characteristics, three factors were used - 'Vendor', 'DaystoKEV' and 'BaseScore'
</p>
<p align="center">
<img width="550" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/c4a87a3d-53b2-4fbd-8cab-483294021990">
</p>
<br>
</p>
<p align="center">
<img width="420" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/78cdb056-5c54-47e1-83d1-054855b155d3">
</p>
