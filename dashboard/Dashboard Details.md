# Dashboard Details

## Link to Dashboard
Please click [here](https://public.tableau.com/app/profile/winnie.nguyenn/viz/RFMAnalysis-Ecommerce/Dashboard2) to see the interactive dashboard on Tableau.

## Dashboard description
The dashboard has 3 main sections, which makes it easy for users to follow the information. 

### 1. Segmentation Information
After a multitude of trials, the following metrics have been used to rank RFM: 

```
#Frequency
IF [Frequency] <1 THEN "0"
ELSEIF [Frequency] <  {FIXED : PERCENTILE([Frequency],0.85)} THEN "1"
ELSEIF [Frequency]< {FIXED : PERCENTILE([Frequency],0.90)} THEN "2"
ELSEIF [Frequency]< {FIXED : PERCENTILE([Frequency],0.95)} THEN "3"
ELSEIF [Frequency]< {FIXED : PERCENTILE([Frequency],0.99)} THEN "4"
ELSE "5"
END

#Recency
IF [Recency] < 60 THEN "5"
ELSEIF [Recency]< 120 THEN "4"
ELSEIF [Recency]< 180 THEN "3"
ELSEIF [Recency]< 365 THEN "2"
ELSE "1"
END

#Monetary
IF [Monetary] <  30000 THEN "1"
ELSEIF [Monetary] < 50000 THEN "2"
ELSEIF [Monetary] < 100000 THEN "3"
ELSEIF [Monetary] < 500000 THEN "4"
ELSE "5"
END
```

Since this analysis only focuses on valuable customers, I used 3 as the cut-off scores for Frequency and Monetary, meaning that I only select those customers who have considerable amount of orders, and spend at least 100000 PKR in total buying goods. The main factor that differentiates the customers is their Recency.

The detailed segmentation is displayed below:

```
IF [New Customers]==1 AND INT([Monetary Ranking]) > 3 AND INT([Freq Ranking]) > 3 THEN "Best New Customers"

ELSEIF (([Recency Ranking] == "1" )
AND (INT([Monetary Ranking]) > 3 ) 
AND (INT([Freq Ranking]) > 3)) THEN "Lost Customers"

ELSEIF (([Recency Ranking]=="2")
AND (INT([Monetary Ranking]) >3 ) 
AND (INT([Freq Ranking]) > 3)) THEN "Hibernating Customers"

ELSEIF (([Recency Ranking]=="3")
AND (INT([Monetary Ranking]) >3 ) 
AND (INT([Freq Ranking]) > 3)) THEN "At-risk Customers"

ELSEIF (([Recency Ranking]=="4")
AND (INT([Monetary Ranking]) >3 ) 
AND (INT([Freq Ranking]) > 3)) THEN "Need-attention Customers"

ELSEIF (([Recency Ranking]=="5")
AND (INT([Monetary Ranking]) >3 ) 
AND (INT([Freq Ranking]) > 3)) THEN "Best Loyal Customers"


ELSE "Others"
END
```

### 2. Dashboard Breakdown

<img src="https://github.com/unguyen14/RFM_Analysis/blob/main/media/whole_section.png"></img>
The 3 sections are divided by the red lines in the image above.
At the top row, there are three text columns, providing an introduction, the target customers, as well as the segmentation information. As for the **Target** and the **Segmentation Information**, the three charts below illustrate them with the visual presentations, which can be followed by the yellow vertical line. 

On the second row, there are three main columns, containing 4 charts. 

<img src="https://github.com/unguyen14/RFM_Analysis/blob/main/media/chart1_info.png"></img>

The first chart describes the growth of revenue since the first order of each quarter. This chart evidences the significant spendings of customers who first placeed their orders in 2018, resulting in a demand to put them in a separate group, called "Best New Customers".
The detailed description can be seen by hovering on the button on the chart.

<img src="https://github.com/unguyen14/RFM_Analysis/blob/main/media/chart3_info.png"></img>

The butterfly chart displays further details about all the valuable customer groups, including the total numbers as well as the revenues. In addition, by hovering over the groups' bars, users can find each group's shopping habits observations. By selecting a group, the dashboard will filter the 2 charts on row 3, showing the preferred payment methods and top 10 categories based on AOV.
<img src="https://github.com/unguyen14/RFM_Analysis/blob/main/media/action_filter.png"></img>

The last part of the analysis is a concluding remark, which summarizes the main insights and suggests the priorities for strategic planning to improve customers' interaction with the website.



