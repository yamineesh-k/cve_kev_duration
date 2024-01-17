# CVE - From Discovery to Exploit
 _Assessing the Time Duration Between Vulnerability Disclosure and Knowledge Base Integration_

**INTRODUCTION**

<p align="justify">
Delving into process lifecycles and understanding the forces shaping each stage is always interesting. This article explores the journey of Common Vulnerabilities and Exposures (CVEs) from the National Vulnerability Database (NVD) to Known Exploited Vulnerabilities (KEV), focusing on the time it takes for this transition – a metric we refer to as 'DaystoKEV' in this article. Though both NVD and CISA have different analysis goals, here is how the journey of a CVE from NVD to KEV looks, at a High Level. 
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
To calculate the 'DaystoKEV', the NVD CVE Data and KEV Data were merged and the difference between 'Published' date from the CVE data and 'Date Added' from the KEV data, in days was calculated. The distribution of 'DaystoKev', as visualized below is skewed to the right, suggesting that a majority of KEVs have lower values (relatively, with peak around 0-1000 days. There is also huge variability in the values and includes values below 0. With this foundational undersstanding, let's explore further.
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
When the average 'DaystoKEV' and 'Number of KEVs' added by Month were visualized on a line and bar chart respectively, we can see a clear 'downward' trend in the average duration and also the number of KEVs added by month. However, we should note that the KEV data only starts in Nov-21 and the initial weeks had a significant backlog of CVEs added that strongly influences the initial trend. The downward trend is also reflective of faster exploitation of published vulnerabilities. As of writing this analysis (15th Jan 2024), we already have a KEV added for a CVE (CVE-2024-21887, Vendor: Ivanti) published in 2024, which is reflective of faster exploitation duration.
</p>
<br>
<p align="center">
<img width="550" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/af5b63ed-037f-4661-ab3e-1656184542f4">
</p>
<p align="justify">
Another approach to explore the trend is to plot the specific duration for each KEV, visualized as a scatter plot (below), with the top vendors (the KEVs are assigned to) colored different, we do see a wider distribution. Notice the Green markers (Microsoft) clutterred in Mid-2022. We also notice that there are KEVs with Negative 'DaystoKev'. There are 50 of such KEVs. This is because the KEV catalog specifically focuses on vulnerabilities with known exploits, so it may list CVEs that are actively being exploited even if they haven't yet been fully analyzed and published on the NVD. The KEV criteria followed by CISA are explained [here](https://www.cisa.gov/known-exploited-vulnerabilities) in detail.
</p>
<br>
<p align="center">
<img width="590" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/fb0e5701-dd52-4c71-bd57-804609ff7799">
</p>
<br>
<p align="center">
<img width="550" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/c4a87a3d-53b2-4fbd-8cab-483294021990">

</p>
<br>
<p align="center">
<img width="550" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/a9e4e5bd-4302-411c-ad84-ac7d5cdaf573">
</p>
<br>
