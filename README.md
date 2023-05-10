# Gender Inequality Study

## Project Team 02 
Jinqi Zhang (jz707) \
Yiming Chen (yc1066) \
Qian Chen \
Yaxin Ye (yy690)

## Summary 
Gender inequality remains a persistent problem globally, with women often facing disparities in accessing high positions, economic opportunities, and education opportunities. A comprehensive investigation of this issue from three perspectives - employment, decision-making, and education - would provide a broader understanding of the obstacles that women encounter in different aspects of their lives. The purpose of this project is to use visualizations to demonstrate gender-based socioeconomic disadvantages and systemic inequality, thereby increasing awareness and driving action toward gender equality.

## Write Up

* Please find the write up here: https://docs.google.com/document/d/1pHGGmaF6TqPOSODUQQRCv55DZGmG9i7YkIGh1uVQKBc/edit#

## Dataset
* ***WMID_Acdemics, WMID_Judiciary, WMID_Business***: These three datasets are the data collections on women and men in decision-making in academics, judiciary, and business fields from European Institute for Gender Equality (EIGE). Each of them contains a number of women and men in key decision-making positions across multiple fields and countries in 2023. 

* ***Gender_paid_unpaid***: The Gender_paid_unpaid dataset is collected from OECD statistics. The data contains time spent in unpaid work and paid work between men and women across multiple countries in 2022.

* ***Gender_Pay_Gap***: The dataset is from the U.S. Bureau of Labor Statistics (BLS) website. It contains the average annual salaries of men and women in different fields. The data have four columns: Women average annual salary, Men average annual salary, Pay gap, and Pay gap as a percentage. 

* ***Diversity_in_different_fields***: The dataset is from the U.S. Bureau of Labor Statistics (BLS) website. It includes the labor market status of the civilian noninstitutional population in the United States who are 25 years and older. The dataset is categorized by women and race, corresponding with employment rates.

* ***Gender_Inequality_Index***: The file contains 2021 gender inequality index values, maternal mortality ratio, adolescent birth rate, the share of seats in parliament, etc. for all the countries in the world. 

* ***All_Indices_Timeseries***: All composite indices and components time series data set contains life expectancy (le), income inequality in income (ineq_inc), gender inequality index (gii), human development index (hdi), etc. of all countries in the world from 1990 to 2021.

* ***ts_explain***: The file is a complementary explanation to all the variables in the All_Indices_Timeseries data set. 

* ***Education***: This dataset is downloaded from *The World Bank* webiste. It contains 6 variables: *Indicator Name*, *Indicator Code*, *Country Name*, *Country Code*, *Year*, *Value*. This dataset includes the education-related gender data of the countries/regions in the world.

* ***Metadata***: This dataset is also downloaded from *The World Bank* webiste. It contains 23 variables: *Indicator Code*, *Indicator Name*, *Aggregation method*, *Dataset*, *Long definition*, etc. This dataset introduces the information of each indicators.

* ***Contextual Indicators***: Just like *Education* and *Metadata* datasets, *Contextual Indicators* is also downloaded from *The World Bank* website. It contains 6 variables, just like *Education* dataset, which are: *Indicator Name*, *Indicator Code*, *Country Name*, *Country Code*, *Year*, *Value*. This dataset several types of data of the countries/regions in the world.

## Code

### Data Cleaning

* ***data_clean_jz.ipynb***: The file contains the data cleaning process for four datasets, including *WMID_Acdemics*, *WMID_Judiciary*, *WMID_Business*, and *Gender_paid_unpaid*. *WMID_Acdemics*, *WMID_Judiciary*, *WMID_Business* are reformatted and combined as a whole dataframe. In the end, it generates two cleaned files *dm_clean.csv* and *work_clean.csv*. 

* ***data_clean_yc.ipynb***: The file contains two parts of the data cleaning process. In the first part, the cleaned 2021 gender inequality index data adds a column for country codes and saves it as *cleaned_gender_ineq.csv*. In the second part,  the cleaned 1990 to 2021 gender inequality index data adds a column for country codes and saves it as *all_year_GII.csv*. All the NA values are removed in the cleanning process.

* ***data_clean_qc.ipynb***: For the *Gender Pay Gap* dataset I didn’t do much cleaning. The dataset is good to use. For the *Diversity in different field* dataset I manually choose 22 big Occupations that we want to explore and then I replace any occurrence of the dash symbol ('-') with NaN. Next converts the values in the *Female* column to integer type after replacing any NaN values with zero and assigns them back to the same column. It also creates a new *Male* column by subtracting the *Female* column from 100. And last, I remove the string 'occupations' from the occupation names to male the plot looks better.


* ***data_clean_yy.qmd***: This file contains the data cleaning and re-organizing part for *Education* dataset. Countries or regions in this dataset are categorized in two ways: *Income Group* and *Region*. *Income Group* contains 4 income groups: *Low-income*, *Lower-middle-income*, *Upper-middle-income*, and *High-income*. *Region* contains 8 regional groups: *East Asia and Pacific*, *Europe*, *Central Asia*, *Latin America & the Caribbean*, *Middle East and North Africa*, *North America*, *South Asia*, and *Sub-Saharan Africa*. These two country categories are made based on the World Bank's grouping standard, which can be found [here](https://datahelpdesk.worldbank.org/knowledgebase/articles/906519-world-bank-country-and-lending-groups). The only difference is that *Europe and Central Asia* of the World Banks is split into two groups: *Europe* and *Central Asia*. The others remain the same.

### Visulization

* ***plot_jz.ipynb***: The file contains the code for visualization of the decision-making dataset and paid vs unpaid datasets. It generates a connected dot plot using Plotly and a scatter plot using Matplotlib and Seaborn.

* ***plot_qc.ipynb***: The file contains the code for the radar plot to show the gender pay gap and horizontally stacked bar plot to demonstrate the gender diversity in different fields, using Plotly.

* ***plot_yc.ipynb***: The file contains the code for the choropleth map plot to demonstrate the gender inequality index across countries, using Plotly.

* ***plot_yy.qmd***: This file contains the code (Plotly) for the interactive line chart which demonstrates the gender parity of education across the groups of countries/regions.

## Dataset Reference

WMID_Acdemics：https://eige.europa.eu/gender-statistics/dgs/indicator/wmidm_educ__wmid_acadsci/metadata \
WMID_Judiciary: https://eige.europa.eu/gender-statistics/dgs/indicator/wmidm_jud_natcrt__wmid_natcrt_supcrt/metadata \
WMID_Business: https://eige.europa.eu/gender-statistics/dgs/indicator/wmidm_bus_bus__wmid_comp_compbm/metadata \
Gender_paid_unpaid: https://stats.oecd.org/index.aspx?queryid=54757 \
Gender_Pay_Gap: https://docs.google.com/spreadsheets/d/1Qih5qBcuTntLbx7G7BzunRSOgGD0b_zc07sTzqiKGn4/edit#gid=1275614270 \
Diversity_in_different_fields: https://www.bls.gov/cps/cpsaat11.htm \
All_Indices_Timeseries: https://hdr.undp.org/sites/default/files/2021-22_HDR/HDR21-22_Statistical_Annex_GII_Table.xlsx \
ts_explain: https://hdr.undp.org/sites/default/files/2021-22_HDR/HDR21-22_Composite_indices_metadata.xlsx \
Gender_Inequality_Index: https://hdr.undp.org/sites/default/files/2021-22_HDR/HDR21-22_Statistical_Annex_GII_Table.xlsx \
Education: https://genderdata.worldbank.org/topics/education/ \
Metadata: https://genderdata.worldbank.org/topics/education/ \
Contextual Indicators: https://genderdata.worldbank.org/topics/education/
