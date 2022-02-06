# Data-Questers-CANDEV2022

# Challenge
Shared Services Canada (SSC) manages and supports IT infrastructure for 43 departments. One of our key metrics includes a customer satisfaction survey which identifies how departments feel SSC is providing service. Another key metric is the length of time it takes SSC to resolve incidents.

SSC’s main Information Technology Service Management (ITSM) tool currently is a tool called Enterprise Control Desk. This tool is used to track the life of service requests, incidents, problems, changes and configuration items. One area of concern is how long it takes for an incident to go from being opened to closed.

Overall, the majority of time we are meeting our targets but in many cases incidents may bounce around the organization resulting in a longer period of time before SSC resolves a ticket. Knowing when a ticket may be misassigned or open for a long period of time would help SSC improve our service delivery to our partners. Using the information provided will help improve our process to properly define which support team needs to be engaged. Additionally, defining the time between when an incident occurs and when SSC actively starts working on an incident would be another indicator to help SSC improve our processes.

Some metrics and questions we have of the data include:

- Average time that incidents spend in a particular status.
- Average time that incidents spend with a particular Support group (Assigned_Group).
- Mean time to restore service (MTRS), are there particular services that are taking longer on average to be restored?
- Are there particular organizations for whom it takes longer on average to restore services?
- Number of times an incident is reassigned during the life of the ticket.
- Is there a correlation between the number of times an incident is reassigned and how long it takes to restore?
- Is there a correlation to certain groups where tickets stay in a particular status that is resulting in longer times to restore service?
- Is there a correlation to certain services where tickets are not resolved as quickly as other services leading to greater MTRS?
- There are many Event Management tickets. What is the difference in incidents ticket including and excluding Event Management tickets?

Note: The metrics and questions have been reordered.
Note: The original data used for this challenge is not posted in this repository. All the data can be found [here](https://drive.google.com/drive/folders/1ULxbHSUbxGwaSufkk8y_aJDgxva1f8Gq?usp=sharing)

# Files
- AVGDATA directory: contains all the csv outputs for ALL data
- AVGDATA_JEM: contains all the csv outputs for JUST EVENT MANAGEMENT tickets (Extension)
- AVGDATA_EEM: contains all the csv outputs for EXCLUDING EVENT MANAGEMENT tickets
- CORR_DATA: contains all the csv outputs of the correlations (determined by p-values from linear models)
- RA_DATA: contains all csv outputs for reassigned tickets
- RA_DATA_EEM: contains all csv outputs for reassigned tickets EXCLUDING EVENT MANAGEMENT
- anova_results.ipynb: cleans and resaves the output files from correlation_test.Rmd
- basic_statistics.ipynb: contains code that answers all the average time questions. Included and modified code from reassignment.ipynb to get basic statistics for this attribute. Also compares just, excluding, and including Event Management Tickets averages.
- correlation_test.Rmd: contains code that answers all the correlation questions using regression analysis (linear models and ANOVA)
- reassignment.ipynb: contains code that calculates the number of times a ticket is reassigned

## Files in Google Drive
- merged_ssc_ticket_data.csv: a data set that combines INCIDENTS.csv and INCIDENTS_OWNER_HISTORY.csv into one file
- ssc_data_no_reassignment.csv (Extension): a data set that only has tickets that have NOT been reassigned based on merged_ssc_ticket_data.csv
- reassignment.xlsx: analysis of ticket reassignment completed in Excel

# Dependencies
The environments used were Python, RStudio, and Excel

## Python (Jupyter Notebooks)
- os: To read files in folder path as well as create folders if they did not exist
- pandas: To deal with loading, manipulating, and writing csv files
- numpy: Functions that pandas uses in the background for quick computations
- IPython: To display dataframes neatly in console
- dython: To find correlation between categorical data and numerical data

## RStudio
- tidyverse: To use for data analysis; general package that is often used
- data.table: To load and save data efficiently
- car: To compute ANOVA analysis

# Design Decisions
- Python was used for quick data manipulations, specifically to do grouped calculations (mean, sum, and count) by the specified attributes in the challenge, and to calculate the reassigned times for each incident ticket. Python was primarily used to answer the questions related to averages
- Rstudio was used for calculating correlations using linear models. Finding correlations with categorical attributes and numerical attributes is difficult. The `lm()` function automatically converts categorical attributes to dummy variables (1-hot encoded) and then performs a regression with the target attribute (Restore time - numerical). `Anova()` is a special linear model where the attributes are categorical. A p-value of <0.05 illustrates that the feature's relationship is significant to the target attribute. The sign of the intercept illustrates whether the attributes are negatively or positively correlated. RStudio was also used to generate visualizations
- Excel was used to do correlation analysis of number of times a ticket is reassigned with restore time. Excel was also used to produce visualizations

R and Excel were the chosen visualization tools as they were easily accessible by the team members

## Next Steps
Ideally, the solution should have been a 2-3 page interactive dashboard that does the calculations in basic_statistics.ipynb, correlation analysis, and a comparison of the major differences between the data including and excluding EVENT MANAGEMENT tickets (could be done in first sheet)  


# Team Members and Contributions
Tejashwar Singh Banafar, Saint Mary's University: Team leader  
Technical skills: SQL

Dennis Huynh, Queen's University: Focused on answering all the average questions (author of basic_statistics.ipynb and anova_results.ipynb). Calculated the correlations between specified attributes using linear models (author of correlation_test.Rmd). Responsible for the GitHub  
Technical skills: Python, R, PowerBI, Tableau, and Git/GitHub

Joonbum Yang, University of Toronto: Focused on creating the visualizations from the outputs of basic_statistics.ipynb,anova_results.ipynb and correlation_test.Rmd. Used Rmarkdown specifically for visualization.    
Technical skills: R, Stata and Python

Fangyi Yu, Ontario Tech University: Focused on answering all the questions regarding reassignment of tickets (author of reassignment.ipynb) as well as correlation questions. Made visualizations and dashboard in Excel(PivotChart)  
Technical skills: Python, Excel, Tableau, GitHub, Tensorflow, Pytorch, Hypothesis Testing
