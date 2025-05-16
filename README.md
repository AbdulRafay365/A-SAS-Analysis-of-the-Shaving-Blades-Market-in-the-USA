# Shaving Blades Market Analysis

This project presents a data-driven analysis of the U.S. shaving blades market.  
The objective is to provide actionable insights for one of the leading brands, BIC, focusing on factors that can enhance their revenue performance.

## General Info

This project uses sales data from various shaving blade brands sold across the United States.  
The focus is on analyzing performance and trends from the perspective of BIC.  
The analysis answers four core business questions aimed at improving market strategies and consumer targeting.

---

## Technologies and Tools

- SAS  
- Microsoft Excel

---

## Setup

1. Download the dataset from the [Data folder](https://github.com/harshbg/Shaving-Blades-Analysis/tree/master/Data).
2. Run the SAS code from [Project_New.sas](https://github.com/harshbg/Shaving-Blades-Analysis/blob/master/Project_New.sas) using SAS.
3. Refer to the project report for explanation and findings.

---

## Code Examples

**Filtering Product Type:**
```sas
proc freq data=a4;
where product_type = 'RAZOR BLADE';
table L2*product_type;
run;
```

**Creating Custom Product Category:**
```sas
data a4;
set a4;
if L2 = 'CARTRIDGES' then type = 0;
else type = 1;
run;

proc format;
value type 0 = 'Cartridges';
value type 1 = 'Disposable';
run;
```

**Logistic Regression with Stepwise Selection:**
```sas
proc logistic data=L1 outmodel=betas1 desc;
class outlet agm agf ethnicity status inc_status marital kids status / param=ref;
model loyal_customer = outlet agm agf ethnicity status inc_status marital kids status / selection=stepwise slentry=0.3 slstay=0.2 expb;
output out=preds predprobs=individual;
run;
```

**K-Means Clustering:**
```sas
proc fastclus data=clus3 maxclusters=4 maxiter=20 list;
id panid;
var recency_score frequency_score monetary_score;
run;
```

---

## Features

- Impact of advertising on unit sales  
- Brand switching trends due to advertising  
- Demographics influencing customer loyalty  
- Product features influencing loyalty

---

## Status

Project Status: Completed

---

## Inspiration

This project is inspired by the original work of Harsh Gupta and team.  
I have adapted and extended their analysis to further explore the shaving blades market.  
Full credit to the original creators: [Original Repository](https://github.com/harshbg/Shaving-Blades-Analysis)

---

## Contact

**Abdul Rafay Mohammed**  
Data Analytics Professional | Business Intelligence Enthusiast | Deloitte Alumni  
Toronto, Canada  
Email: abdulrafaymohammed365@gmail.com  
GitHub: [AbdulRafay365](https://github.com/AbdulRafay365)  
LinkedIn: [linkedin.com/in/abdulrafaymohammed365](https://www.linkedin.com/in/abdulrafaymohammed365)  
Tableau Portfolio: [public.tableau.com/profile/abdul.rafay.mohammed2129](https://public.tableau.com/app/profile/abdul.rafay.mohammed2129)

---

*Note: This project is a personal adaptation and extension of the original work by Harsh Gupta and team. All original content and analysis are credited accordingly.*

Feel free to replace any placeholder links or information with your actual details as needed. Let me know if you need further assistance!
