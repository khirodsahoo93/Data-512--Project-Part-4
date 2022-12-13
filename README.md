
## Goal
The goal of this project is to investigate the implications of Covid-19 pandemic on unemployment rate and market hotness index in the Hamilton county, Ohio.

## Research Questions

Questions: 

- How was the unemployment rate affected during covid 19, and were all economic sectors affected equally?

- How was the housing market sentiment of people during covid19 when many people were facing financial burdens, and what segment of people benefitted from this boom?

Hypothesis: 

- While the overall unemployment rate in the USA increased, I expect Hamilton county to show similar trends in the unemployment rate.

- With the boom in the housing industry in the USA, the market hotness score will also increase in Hamilton county, Ohio.


## Data Sources Used
For the analysis we are using 5 data sources:

- `Market Hotness Index Dataset [HOSCCOUNTY39061.csv]` - contains monthly hotness index score from 2018 to 2022
- `Unemployment rate Dataset[OHHAMI1URN.csv]` - contains monthly unemployment rate from 1990 to 2022
- `Employees growth by economic sectors Dataset` - contains monthly time series data indicating the growth of employees in each super sector for Cincinnati county.
- `US mask mandate dataset` - from common analysis
- `US daily confirmed cases` - from common analysis

## Repo structure

```bash

├── pandemic_analysis_extended.ipynb
├── README.md
├── LICENSE
├── Input Data
│   ├── Employment by Industry Sector.csv
│   ├── HOSCCOUNTY39061.csv
│   └── OHHAMI1URN.csv
│   ├── RAW_us_confirmed_cases.csv
│   ├── mask-use-by-county.csv
├── Data 512- Final Report.pdf
├── Plots
│   ├── Confirmed cases Vs Hotness score.jpeg
│   ├── Confirmed cases Vs Hotness score_2.jpeg
│   ├── Confirmed cases Vs unemployment rate.jpeg
│   ├── Confirmed cases Vs unemployment rate_2.jpeg
│   ├── Face_Masks_Required_in_Public_policy.jpeg
│   ├── Monthly confirmed cases.jpeg
│   ├── Monthly growth in employees.jpeg
│   ├── Monthly unemployment rate.jpeg
├── Previous analysis
│   ├── Common Analysis
│   ├── Extention plan

```

### Methodology
- *Data Cleaning*:
The 3 datasets discussed above for the extended analysis are on a monthly level, and the US daily confirmed cases data is also standardized to a monthly level for further merging and easier analysis.
- *EDA*:
After cleaning the data and ensuring the continuity of all the time series data, I first performed exploratory data analysis. The time series plots for the unemployment rate, hotness score for Hamilton county, and employee growth rate by different economic sectors are analyzed. 
- *Correlation*:
The Pearson correlation between the unemployment rate and covid confirmed cases and the market hotness index and covid confirmed cases were checked to obtain a preliminary sense if my hypothesis is right or wrong. To validate the results further, I performed regression analysis keeping just one predictor at a time.
- *Regression analysis*:
I checked the relationship between the dependent ( unemployment rate ) and the independent variable ( covid confirmed cases) through the beta coefficient. I also tested the significance of the independent variables from their associated p-value. A similar analysis was also performed with the hotness score as the dependent variable and monthly confirmed cases as the independent variable.


## Charts and Findings

The market hotness index decreased initially after the onset of covid in March 2020 which makes sense as there were lockdowns and other policies like mask mandates were in place. But then the score increased even when the cases increased after June 2021 similar to our initial theory and research. It kept increasing until Jan 2022 when the omicron variant was spreading rapidly and the cases were at an all-time peak.

 ![1](https://github.com/khirodsahoo93/Data-512--Project-Part-4/blob/main/Plots/Confirmed%20cases%20Vs%20Hotness%20score.jpeg)
 
 During the  start of covid in Mar 2020, the unemployment rate spiked and during the peak of covid in Jan 2022 too, the unemployment rate started increasing again. But in other time periods during covid, the unemployment rate decreased after rising which could be due to various policies introduced by the government like covid relief funds and welfare schemes.
 ![2](https://github.com/khirodsahoo93/Data-512--Project-Part-4/blob/main/Plots/Confirmed%20cases%20Vs%20unemployment%20rate.jpeg)
 
 Until covid 19, the employment growth rate was almost constant across all sectors but after covid, some sectors were affected more than others - the leisure and hospitality sectors were impacted the most among all the sectors.
 ![3](https://github.com/khirodsahoo93/Data-512--Project-Part-4/blob/main/Plots/Monthly%20growth%20in%20employees.jpeg)

## License
- This assignment code is released under the MIT License.
- The license for the datasets used are mentioned in the report [Data 512- Final Report.pdf]

## Research Implications
From the above analysis, we realized that the immediate impact of the covid-19 is quite visible. With the outbreak of covid-19, the unemployment rate dipped and the market hotness index plummeted as well. This observation lines up with the research in section 2, where we read about the immediate impact of covid-19 on the unemployment rate and the housing market.
However, we expected the unemployment rate to keep increasing with the increase in the number of cases. This is quite not what we observed in our analysis. The unemployment rate improved during the covid-19 period. This aligns with the article from US labor statistics where it was mentioned that the unemployment rate started decreasing towards the end of the second quarter.
Also, as opposed to what was expected, the relationship between unemployment and hotness score with rising covid cases was not linear. From the Pearson correlation, we found a weak correlation between the variables. The nonlinear behavior could be because of many external factors like pharmaceutical and non-pharmaceutical interventions during covid-19. Unemployment and the housing market are closely tied to humans as people need jobs in order to earn and survive.  Many people lost jobs, and businesses were shut down while new jobs were also created. Also, owning a house is an American dream, and people were able to buy homes due to plummeting mortgage rates making many dreams come true. This analysis helped me to understand the extent to which an event like a pandemic could impact people’s lives.

