# Data-512-HW4--Part1
Part1 Common Analysis


## Goal

During the last three years we all have been experiencing a global pandemic. This has been tragic and disruptive to many countries and has taken a deep personal toll on many individuals and their families. 
One aspect that has been hard to miss in the last three years is the datafication of the pandemic. That is, many aspects of the individual toll of the pandemic have been collected, aggregated and re-represented as data. This datafication gives us the privilege to examine the pandemic from potentially many different perspectives to understand how it has changed lives and how it has changed society. To be honest, we are actually at the very beginning of understanding and comprehending these impacts.

This is the part one of the final assignment of the Data 512 and the goal is to perform a collective analysis while answering common research questions on the pandemic. Every student is assigned one county to perform the analysis. The county assigned to me was Hamilton of Ohio state.

## Data Sources Used
For the analysis we are using 3 data sources:

[1] `RAW_us_confirmed_cases.csv ` - The file is obtained from the Kaggle repository of John Hopkins University COVID-19 data [https://www.kaggle.com/datasets/antgoldbloom/covid19-data-from-john-hopkins-university]. This data is updated daily. You can use any revision of this dataset posted after October 1, 2022.

[2] `Mask mandate Dataset` - The CDC dataset of masking mandates by county. Note that the CDC stopped collecting this policy information in September 2021.

[3] `Mask compliance survey dataset` - The New York Times mask compliance survey data.

Note- The first dataset has many null values in few fields like source_action, Face_Masks_Required_in_Public.

Special Considerations:

- The [1] data is only for the confirmed cases while there may be many cases which are not reported. Also the tests conducted in early phase were not consistent and could take 1 day to several days to get results. Hence, we can see several fluctuations while visualizing the data. To smoothen the curve, rolling average of 7 days was done.

### INPUT

A sample table from the confirmed cases data `RAW_us_confirmed_cases.csv ` :
```sh
Province_State	Admin2	UID	        iso2	iso3	code3	FIPS	Country_Region	Lat	        Long_	...	10/22/22	
Alabama	        Autauga	84001001	US	    USA	    840	    1001.0	US	            32.539527	-86.644082	...	18480	
Alabama	        Baldwin	84001003	US	    USA	    840	    1003.0	US	            30.727750	-87.722071	...	65895	
Alabama	        Barbour	84001005	US	    USA	    840	    1005.0	US	            31.868263	-85.387129	...	6926	
Alabama	        Bibb	84001007	US	    USA	    840	    1007.0	US	            32.996421	-87.125115	...	7560		
Alabama	        Blount	84001009	US	    USA	    840	    1009.0	US	            33.982109	-86.567906	...	17286		
```

A sample table from the `Mask mandate Dataset` :

```sh
State_Tribe_Territory	County_Name	        FIPS_State	FIPS_County	date	order_code	Face_Masks_Required_in_Public	Source_of_Action	URL	Citation
OH	                     Hamilton County	39	        61	        4/15/2020	2	    NaN	                            NaN	                NaN	NaN
OH	                     Hamilton County	39	        61	        4/16/2020	2	    NaN	                            NaN	                NaN	NaN
OH	                     Hamilton County	39	        61	        4/10/2020	2	    NaN	                            NaN	                NaN	NaN
OH	                     Hamilton County	39	        61	        4/11/2020	2	    NaN	                            NaN	                NaN	NaN

```

A sample table from the `Mask compliance survey dataset`:

```sh
COUNTYFP	NEVER	RARELY	SOMETIMES	FREQUENTLY	ALWAYS
0	        1001	0.053	0.074	0.134	0.295	0.444
1	        1003	0.083	0.059	0.098	0.323	0.436
2	        1005	0.067	0.121	0.120	0.201	0.491
3	        1007	0.020	0.034	0.096	0.278	0.572
4	        1009	0.053	0.114	0.180	0.194	0.45
```

## Repo structure

```bash

├── Data512-part1.ipynb
├── README.md
├── LICENSE
├── data
│   ├── RAW_us_confirmed_cases.csv
│   ├── mask-mandate.csv
│   └── mask-use-by-county.csv
├── Reflection_Statement.pdf
├── Visualization_Explanation.pdf
├── plots
│   ├── Number_of_cases_cumulative.png
│   ├── Number_of_cases_daily.png
│   ├── Infection_rate.png
│   ├── Second_order_differencing_of_Infection_Rate'.jpeg
│   ├── Second order difference of the numner of COVID cases daily.jpeg

```
## Output files

The example of screenshots from the analysis:


## License
- This assignment code is released under the MIT License.
- The Wikipedia English language articles data source is released under the CC-BY-SA 4.0 license.




