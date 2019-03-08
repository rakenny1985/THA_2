# THA_2
## Project Name: USAID Disbursement Research
### Project Summary
* This is a research project for a Data Management class at the LBJ School of Public Policy in Austin. While currently in progress, it the goal is to merge open source data into an analyzable dataframe to answer the question: How does USAID decide which countries get the most foreign aid? 
### Previous Work on the Project
* No direct work prior to this project. 
### Funding Information
* The absurd amount of student loan debt that is funding my master's degree $$$ :). 
### Primary Contact Information
* I'm not sure I want to put anything here. To be discussed. 
### Additional Collaboration on Project
* No direct collaboration. A professor from the LBJ School is providing mentorship. 
### Data and Supporting Information
* **Source #1**: USAID Foreign Aid Explorer; Country Summary; xlsx - [FAE: Data](https://explorer.usaid.gov/data.html)
		
    * What is it?: A table of all the US donations and obligations of foreign aid by year and by country. It is in both current USD and constant USD. 
		
    * The rows represent each country per a specific year of aid. The attributes are: [‘unique_id’, ‘country_code’, ‘country_name’, ‘region_id’, ‘region_name’, ‘income_group_acronym’, ‘income_group_name’, ‘transaction_type_id’, ‘transaction_type_name’, ‘year’, ‘current_amount’, ‘constant_amount’].  The attribute headers are fairly self-explanatory, however for definition of an “obligation” vs. a “disbursement” there is a USAID pdf Data Dictionary ([FAE: Data](https://explorer.usaid.gov/data.html)).  
		
    * Manipulation in Excel: To ensure the data was properly identifiable,  I added a column for ‘unique_id’ which is an excel concatenation of the country name+year. The original data included replications of each disbursement or obligation made (ie. from USAID or DoD) but did not include unique $ amounts (just the total for the year). As such I deleted all of the replications. I checked 3 random samples of country by year back to the USAID dashboard [FAE: Dashboard](https://explorer.usaid.gov/aid-dashboard.html) to ensure the totals were correct. No additional excel changes were made. An original has also been saved in my project folder. 
	
* **Source #2**: DePaul University Quantitive Reasoning Center; Excel Files; _Presidents.xls_ - [QRC Home Page](http://qrc.depaul.edu)
		
    * What is it?: A table of all US Presidents by term length and inauguration date; includes college, age upon taking office, occupation, political party and various election results
		
    * Manipulation in Excel: I manipulated this data in excel for ease of use in my data frame merge later in Python. I wanted this workbook so I could link each US president from the start of USAID data (1946) and their political party to the year of foreign aid obligations and disbursements. As such, I deleted unnecessary election result columns and created a column for year in office (inauguration year+total years in office). I then copied the president name and other attributes (age, school, etc.) to have corresponding attributes with each specific year (instead of one president row for a range of years). For years in which power changed, I have hard keyed both presidents that held office for part of the year and their respective parties. I may go back and change this if it’s unhelpful as the incoming president likely wouldn’t have any direct aid decision making (for the portion of the year they actually held office which in /most/ cases is Nov-Dec). I validated a sample of president name and year via a google search. 
		
    * The attributes are: [‘President’, ‘Year’, ‘Age at inauguration’, ‘Political Party’, ’Occupation’, ‘College’] and are all self-explanatory. 
	
 * **Source #3:** Center for Systemic Peace: [Mission](https://www.systemicpeace.org/mission.html); INSCR Data; Polity IV Annual Time-Series, 1800-2017; Excel Series
		
    * What is it?: Per their website: “*Polity IV Project, Political Regime Characteristics and Transitions, 1800-2017,* annual, cross-national, time-series and polity-case formats coding democratic and autocratic “patterns of authority” and regime changes in all independent countries with total population greater than 500,000 in 2017 “
	
   * Manipulations in Excel: I saved two versions of this file; one original and one unique. I sorted all data by year and deleted any entries prior to 1946 as there is no data in USAID to match. I also created a concatenated unique id in the same fashion as in the USAID data above. I also found two duplicate entries by comparing replications in the “year” and country” columns and deleted them (Yugoslavia 1991 and Eritrea 1993). No other manipulations made. 
		
    * The attributes are: [‘unique_id’, ‘cyear’, ‘ccode’, ‘scode’, ‘country’, ‘year’, ‘flag’, ’fragment’, ‘democ’, ‘autoc’, ‘polity’, ‘polity2’, ‘durable’, ‘xrreg’, ‘xrcomp’, ‘xropen’, ‘xconst’, ‘parreg’, ‘parcomp’, ‘exrec’, ‘exconst’, ’polcomp’, ‘prior’, ‘emonth’, ‘eday’, ‘eyear’, ‘eprec’, ‘interim’,  ‘bmonth’, ‘bday’, ‘byear’, ‘bprec’, ‘post’, ‘change’, ‘d4’, ‘sf’, ’regtrans’]. The users manual with variable definitions can be found here: http://www.systemicpeace.org/inscr/p4manualv2017.pdf. 
		
    * Many of the attributes contain subjective calculations and weighting (which is reasonable given the nature of the characteristics they are trying to conceptualize such as ‘democracy’) so I will need to put a bit of time in to understanding the major components and assumptions made. However for this exercise I wanted to use this data to give an idea on the level of institutionalized democracy (‘democ’) and institutionalized autocracy (‘autoc’)
### Organization and Naming Conventions Used for the Data
* Organization: All files (including PDFs, .xls, .xlsx, word) used in support of Python analysis will be kept in this repository in their original form (post user modifications noted above). Primary Python coding and analysis will be performed in [Google Colaboratory](https://colab.research.google.com/) for ease of edit and transfers to this repository. Primary Python coding file is the only .ipynb file-type. 
* Naming Conventions: Naming conventions for files is in process. 
### Next Steps	
  * I’d like to merge additional country data on: 
  	* GDP; GDP/capita 
	* Conflict 
	* Natural and Humanitarian disaster status  
	* International institution alliances - political
	* International institution alliances - economic
	* Foreign lobbying dollars in the US by country
