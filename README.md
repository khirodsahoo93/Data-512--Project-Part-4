
## Goal
The goal of this project is to investigate the implications of Covid-19 pandemic on unemployment rate and market hotness index in the Hamilton county, Ohio.

## Data Sources Used
For the analysis we are using 5 data sources:

- `Market Hotness Index Dataset` - contains monthly hotness index score from 2018 to 2022
- `Unemployment rate Dataset` - contains monthly unemployment rate from 1990 to 2022
- `Employees growth by economic sectors Dataset` - contains monthly time series data indicating the growth of employees in each super sector for Cincinnati county.
- `US mask mandate dataset` - from common analysis
- `US daily confirmed cases` - from common analysis


### Data Descriptions

*Market Hotness Index Datasett*

| Column | Description |
| ------ | ----------- |
| name   | title/name of the politician
| url    | url of the wikipedia page
| country| country associated with the politician

*Population dataset*

| Column | Description |
| ------ | ----------- |
| Geography   | Country and Regions
| population (in millions) | Population in millions

Note-The above data contains some rows that provide cumulative regional population counts. These rows are distinguished by having ALL CAPS values in the 'geography' field (e.g. AFRICA, OCEANIA)

### Methodology
- *Data Cleaning*:
The 3 datasets discussed above for the extended analysis are on a monthly level, and the US daily confirmed cases data is also standardized to a monthly level for further merging and easier analysis.
- *EDA*:
After cleaning the data and ensuring the continuity of all the time series data, I first performed exploratory data analysis. The time series plots for the unemployment rate, hotness score for Hamilton county, and employee growth rate by different economic sectors are analyzed. 
- *Correlation*:
The Pearson correlation between the unemployment rate and covid confirmed cases and the market hotness index and covid confirmed cases were checked to obtain a preliminary sense if my hypothesis is right or wrong. To validate the results further, I performed regression analysis keeping just one predictor at a time.
- *Regression analysis*:
I checked the relationship between the dependent ( unemployment rate ) and the independent variable ( covid confirmed cases) through the beta coefficient. I also tested the significance of the independent variables from their associated p-value. A similar analysis was also performed with the hotness score as the dependent variable and monthly confirmed cases as the independent variable.


## Output files

`wp_countries-no_match.txt` - This file contains the names of the politicians for which no response was found.

`wp_politicians_by_country.csv` -This file contains the name of the politicians ('article title') with 'country','region','population','revision_id' and 	'article_quality' for which respone was found

## License
- This assignment code is released under the MIT License.
- The Wikipedia English language articles data source is released under the CC-BY-SA 4.0 license.


## Research Implications

### Special Considerations

1. The population dataset contained name of both countries and regions in the Geography column. The population against the regions were the sum of population of all the countries preceded by it. So a data cleaning operation was performed to keep only countries name in the Geography columns and mapped the corresponding regions against them with the lowest hierarchy.
2. In the politician datasets, there were duplicate rows which were removed but the duplicates based on name and country were retained so that they can be used to calculate articles per capita.
3. Since, the population is in millions, there were countries which may have low populations due to which population in millions is 0. This turned out problematic when ratios were calculated.

What I Learned ?

- Reproducibility is hard

In my own code, I faced problems when I was trying to re-run a snippet. There were different errors everytime I was re-running. Also, when I was calling the API between different days, I was surprised to see that some pages gets deleted the next day which also impacted few of my figures. 

- Results may be biased

Since , the data is crawled from the wikipedia website and even if several preprocessing had been done to get a cleaner data , there is still a chance that some articles may not have been successfully crawled which could lead to wrong interpretation of the results. More details on how the data was captured could validate my hypothesis. Also, there is a chance of linguistic bias in the data as few non-english speaking nations may be educated but their english may be slightly different leading to scoring low for those articles. 

What biases did you expect to find in the data (before you started working with it), and why? 

- I expected to see the developed nations to have high coverage as compared to underdeveloped nation as I assumed that developed nations would have higher literacy rate and hence would have more number of articles.

Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research, or make business decisions) might create biased or misleading results, due to the inherent gaps and limitations of the data?

- The exit poll survey that is often used to predict election results has biases because the survey responders could only be the people who are willing to participate. Also, the survey may done on regions which may not be the right representative of the entire population who are going to vote.

How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed? 

- For one instance, the researcher can include english speaking population numbers in each country. So that the articles per capita can be calculated based on english speaking population instead of total population to give a fair comparison
