# Valuable Customer Segmentation with RFM Analysis Dashboard 
## Project Overview

<img src="https://github.com/unguyen14/RFM_Analysis/blob/main/media/whole.png"></img>

This data visualization dashboard analyzes valuable customers shopping behaviors on a Pakistan e-commerce website based on RFM, using Tableau to better describe these groups.

**Methods:**
- Datasets Preparations: Python
- Visualization: Tableau

## Project Motivation

Understanding customers' shopping behaviors thoroughly can provide significant leverage for companies in the era of online shopping boom. By studying the data from March 2016 to August 2018, this analysis aims to identify different group of valuable customers, using **Recency - Frequency - Monetary** method, which can provide insights for business strategy planning. This micro-scoped analysis focuses on segmenting only very valuable customers, whose Monetary and Frequency scores are greater than 3 (on a scale of 1 to 5), due to their significant contribution to the total revenue (35%) despite making up of less than 7% of total number of customers. 

The dashboard has three main sections, divided horizontally so users can follow easily. More details about the dashboard design can be found in [this document](https://github.com/unguyen14/RFM_Analysis/blob/main/dashboard/Dashboard%20Details.rmd). 

## Link to dashboard
Please click [here](https://public.tableau.com/app/profile/winnie.nguyenn/viz/RFMAnalysis-Ecommerce/Dashboard2) to see the interactive version on Tableau.
 
## Project Directory
```
| - RFM_Analysis
|   -- dashboard                                        Contains detailed description and link to dashboard
|      --- Dashboard Details.rmd
|   -- dataset                                  
|      --- Ecom_cleaned_Data.xlsx                       Contains cleaned data 
|      --- Pakistan Largest Ecommerce Dataset.csv       Original dataset
|      --- RfM_analysis.ipynb                           Contains Python codes to clean data
|   -- media                                            Contains image files for illustration
|      --- action_filter.png
|      --- chart1_info.png
|      --- chart3_info.png
|      --- whole.png
|   -- .gitignore                                       Contains ignored file
|   -- LICENSE                                          MIT License
|   -- README.md                                        Project Overview
```

## Challenges
The main challenge of this analysis is to determine the score intervals for the RFM, due to the extremely skewed values and outliers of the dataset. For the Frequency, I used percentiles to assign scores, while I had to assign some fixed values as the cut-off points for Monetary as well as Recency. This decision was made after various experiences with grouping and observing the changes in groups' charateristics, as well as identifying reasonable values for this particular dataset. For instance, Recency was determined based on time intervals (months), which explained the shopping habits more intuitively. A similar approach was applied for Monetery, taken into consideration the currency difference and the local income. 

## Future considerations
I will consider running the calculations in Python in order to achieve better accuracy, as well as experimenting with unsupervised learning algorithms in order to explore different way to group customers together.



