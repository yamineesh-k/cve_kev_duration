# CVE - From Discovery to Exploit
 _Assessing the Lag Between Vulnerability Disclosure and Knowledge Base Integration_

**INTRODUCTION**

<p align="justify">
In the ever-evolving landscape of cybersecurity, staying ahead of emerging threats is crucial. Patching critical vulnerabilities is paramount, but understanding the timeline from discovery to exploitation is equally important. This article explores the journey of Common Vulnerabilities and Exposures (CVEs) from the National Vulnerability Database (NVD) to Known Exploited Vulnerabilities (KEV), focusing on the time it takes for this transition – a metric we refer to as 'DaystoKEV' in this article. Here is how a typical process to add a CVE to the KEV looks, at a High Level.
</p>
<br>
<p align="center">
<img width="480" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/1d7c084e-802b-4555-be0a-48dfb45bc5a9">
</p>
<br>

CALCULATING DAYS TO KEV

<br>
<p align="justify">
To calculate the 'DaystoKEV', the NVD CVE Data and KEV Data were merged and the difference between 'Published' date from the CVE data and 'Date Added' from the KEV data, in days was calculated. The distribution of 'DaystoKev', as visualized below is skewed to the right, suggesting a majority of KEVs having lower values, with peak around 0-1000 days. There is also huge variability in the values and includes values below 0.
</p>
<br>
<p align="center">
 <img width="400" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/d0379b0b-b21d-4019-93f2-18aaa6639ac4">
	</p>
<br>
TREND AND TIME DISTRIBUTION
<br>
<p align="center">
<img width="590" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/19b4dee3-b7ad-4f9b-a24f-c8782d89408b">
</p>
<br>
<p align="center">
<img width="590" alt="image" src="https://github.com/yamineesh-k/cve_kev_duration/assets/76024628/fb0e5701-dd52-4c71-bd57-804609ff7799">
</p>
<br>
