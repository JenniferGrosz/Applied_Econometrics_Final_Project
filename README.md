# Applied_Econometrics_Final_Project
OMSBA 5300 Winter 2021 Data Translation Challenge

#### Author: Jennifer Grosz, Arunima Roy

## The Task
You work for a company in the retail sector. Your company knows how well they’re weathering the pandemic, but they are having difficulty figuring out what the effect has been on the rest of the retail sector and the rest of the economy. Everyone is being tight with their numbers!

So, they’ve brought you on and pointed you towards the IPUMS release of the Current Population Survey, which the government often uses to understand changes in employment.

Why employment data? They figure that revenues can be misrepresented, or might be affected by government aid. But employment in an industry can tell you a lot about how well that industry is doing!

They don’t know exactly what analyses they want you to run or variables they want you to use - figuring that out is your job. Below is the question they'd like answered from this analysis:
- Retail needs to worry about who has money to spend - what has changed about who is working and earning money?


# Reason for running the analysis we ran
Prior, we explored how COVID-19 has affected the health of the retail industry as measured by employment and how the retail industry fared relative to the other industries. In the last part of this analysis, we dive into the demographics of individuals who are working and earning money. 

The objective for this analysis was to determine who has money to spend and what has changed about who is working and earning money. In order to satisfy this objective, we have generated the following linear probability models, all of which have the intended goal of presenting a clear understanding of who is more likely to be currently working and earning money at this time through the comparative lens of each analysis:

Gender Analysis – Our first regression model is an analysis of the associated effect being female during the COVID-19 pandemic has on a person’s probability to be employed relative to being male. Specifically, this model is addressing our objective through the lens of who has a higher probability to be employed, a person who is female or male.

Marriage Status Analysis – Our second regression model is an analysis of the associated effect being married during the COVID-19 pandemic has on a person’s probability to be employed relative to not being married. Specifically, this model is addressing our objective through the lens of who has a higher probability to be employed, a person who is married or not married.

Age Generation Analysis – Our third regression model is an analysis of the associated effect being a certain age generation during the COVID-19 pandemic has on a person’s probability to be employed relative to other age generations. The age generations for people included in this analysis are Generation Z, Millennials, Generation X, and Baby Boomers. Specifically, this model is addressing our objective through the lens of who has a higher probability to be employed, a person from the Baby Boomer generation or Gen X or Millennial or Gen Z.

Highest Educational Attainment Analysis – Our fourth regression model is an analysis of the associated effect having a certain educational achievement level during the COVID-19 pandemic has on a person’s probability to be employed relative to other educational achievement levels. The education level categories included in this analysis are below a High School graduate, High School graduate, Associate degree, Bachelor’s degree, Master’s degree, Professional degree, and Doctorate Degree. Specifically, this model is addressing our objective through the lens of who has a higher probability to be employed, a person with a Doctorate Degree or Professional Degree or Master’s degree or Bachelor’s degree or Associate degree or High School graduate or below High School graduate.

Racial Category Analysis – Our fifth regression model is an analysis of the associated effect being a certain race during the COVID-19 pandemic has on a person’s probability to be employed relative to other racial categories. The racial categories included in this analysis are White, Black, American Indian/Aleut/Eskimo, Asian, Hawaiian/ Pacific Islander and Mixed races. Specifically, this model is addressing our objective through the lens of who has a higher probability to be employed, a person who is White or Black or American Indian/Aleut/Eskimo or Asian or Hawaiian/ Pacific Islander or Mixed.

# How our analysis answers "Who has money to spend? - What has changed about who is working and earning money?"
For each of the five analyses conducted our regression models are constructed in a similar general format that sets a binary variable indicating employed or not employed as the dependent variable, our measure of interest (gender, marriage status, age generation, educational achievement level, and racial category) interacted with a binary COVID-19 variable since this is our true measure of interest and will present a measure for the effect COVID-19 has on the given demographic variable of interest. The COVID-19 variable indicates whether the date from which the relevant associated data was collected prior to April 2020 which has been assigned as the “pre-COVID-19” period in our data set or the relevant associated data was collected from a time after February 2020, which has been assigned as the “current COVID-19” period in our data set. We then also included an interaction between the binary COVID-19 indicator variable with an incrementally increasing variable to represent the passing of time measured in 1-month units. We included this additional interaction in our model to control for the correlation we believe exists between time and the COVID-19 pandemic variable in our model. To verify the validity of our assumption about a potential correlation, we ran a correlation matrix between the time and COVID-19 variables and found that our assumption was accurate. The test showed a .8519 correlation coefficient which is to be interpreted as the indication of a strong correlation between time and the COVID-19 variables in our data set.

It is our belief that determining who is working and earning money can be answered through an analysis of different demographic elements. Alone, one of our models would not properly answer this question, but together the conclusions drawn from the results of our analysis can build a clear picture of the type of person who is most likely to be working and earning money at this time that our company in the Retail sector should be focusing on for marketing initiatives and targeting in sales directives.

## Data Set Used for Analysis
The data used in this analysis is from IPUMS CPS. This data is at the person level and provides data per month for each year over a period between January 2019 - January 2021. 

This data has been filtered to only include respondents who indicated that they participated in the labor force during the preceding week and we made the decision to not include people who are employed by the US Military. It was our assumption that the COVID-19 pandemic would not affect people employed by the military in the same way it has for people not employed by the US Military.

We then created binary dummy variables for the identification of each respondents gender, marriage status, and employment status in addition to coded categorical variables for the identification of each respondents age generation, educational achievement level, and racial category.

Gender is identified through a variable named “female” and it indicates whether each person in the sample is male (represented as 0) or female (represented as 1). We determined the assignment values for this variable based on the respondents original coded response for the variable “sex” recorded in the extracted IPUMS CPS data. 

Marriage status is identified through a variable named “married” and it indicates whether the respondent is married (represented as 1) or not married (represented as 0). We determined the assignment of value for this variable based on each respondents original coded response for the variable “marst” recorded in the extracted IPUMS CPS data. Married people have been defined as people who are married, spouse present and all other categories have been assigned to a value that denotes not married.

Employed people are identified through a variable named “employed” and it indicates whether each person in the sample is employed (represented as 1) or unemployed (represented as 0). We determined the assignment of value for this variable based on each respondents original coded response for the variable “empstat” recorded in the extracted IPUMS CPS data. Employed people have been defined as people who are at work or have a job but may have not worked since last week. Unemployed people are denoted in the data set as people who are unemployed, unemployed people who are experienced workers and unemployed people who are new workers. 

Age generation categories are identified through a variable named “ageGeneration” and it indicates the age generation for each person in the sample as Generation Z (people age 16 - 22), Millennials (people age 23 - 38), Generation X (people age 39 – 54) and Baby Boomers (people age 55-73). We determined the assignment value for this variable based on each respondents original response for the variable “age” recorded in the extracted IPUMS CPS data. It was our belief that since our data covered January 2019 – January 2021, the coding of these age generations would be accurate for the time periods in which they were recorded.

Educational attainment categories are identified through a variable named “educationCategories” and it indicates the highest education level attained for each person in the sample as below High School graduate, High School graduate, Associate Degree, Bachelor’s degree, Master’s Degree, Professional Degree or Doctorate Degree. We determined the assignment value for this variable based on each respondents original coded response for the variable “Educ99” recorded in the extracted IPUMS CPS data. 

Racial categories are identified through a variable named “racialCategories” and it indicates the race of each person in the sample as White, Black, American Indian/Aleut/Eskimo, Asian, Hawaiian/Pacific Islander or Mixed. We determined the assignment value for this variable based on each respondents original coded response for the variable “race” recorded in the extracted IPUMS CPS data.

Finally, we generated a date variable “year_month” by uniting “year” and “month” for which the respondents data was recorded in the extracted IPUMS CPS data. With this variable we removed all data from March 2020 from our data set in order to eliminate uncertainty around when the COVID-19 pandemic began in the US. By removing March 2020 from our data set we have established a clear timeline for determining data collected before COVID-19 and during COVID-19 as the pandemic is still ongoing in the US today, this difference is represented through a binary variable named "covid" in our data set. We also created an incrementally increasing variable to represent the passing of time measured in 1-month units

Our resulting data set contains the following variables:
year: survey year in which the data was collected 

month: survey month in which the data was collected 

year_month: custom date variable in the form of "YEAR-M"

wtfinl: final basic weight, used to weight the data accurately 

ageGeneration: custom variable created to put the different ages in the appropriate generational group

racialCategories: custom variable created from the 'race' variable 

female: dummy variable to indicate female = 1 and male = 0

married: dummy variable to indicate whether you are married or other, married = 1 and other = 0

employed: dummy variable to indicate employment; employed = 1 and unemployed = 0

educationCategories: custom variable to group some of the highest education levels of the individuals 

covid: dummy variable to indicate whether the associated data was collected on a date prior to April 2020 or after February 2020; Prior to April 2020 = 0, After February 2020 = 1

time: incrementally increasing variable to represent the passing of time measured in 1-month units

# Interpretation and Presentation of Regression Results 
The regression model we deemed most appropriate for this analysis was the linear probability model with different interactions between the COVID-19 and the various demographic variables including a control for the effect of time via an interaction element in the models between COVID-19 and time. 

#### Gender Analysis
The first regression analysis was conducted to determine the associated effect of being a female during the COVID-19 pandemic has on a person's probability of being employed relative to being male during the COVID-19 pandemic.   
![Gender Analysis](/Images/one.png)

For this regression analysis, what we really want to focus on is the coefficient for the interaction between the female and COVID-19 variables in our model as that measures the effect of being female during the COVID-19 pandemic on the probability of being employed relative to being male.

Prior to the COVID-19 pandemic, we see the effect of being female is associated with approximately 0.23 percentage points higher in the probability of being employed relative to being male. 

However, once the COVID-19 pandemic started, we see the effect of being female during the COVID-19 pandemic is associated with approximately 0.78 percentage points lower in the probability of being employed relative to males during the COVID-19 pandemic.

![Employment by Gender](/Images/two.png)
Figure 1.

Above in Figure 1 during approximately March of 2020, you will see an immediate decline in the employment rate for both men and women resulting from state mandated stay-at-home orders that were put in place due to the COVID-19 pandemic. The drop in employment rates is understandable given our knowledge of how the country-wide state-mandated quarantines  impacted individuals employed in industries where working from home was not an option, so these stay-home mandates resulted in a spike of employees being laid off. 

Since the beginnings of quarantine, employment rates have gone up but given the continued pandemic-induced State of Emergency that the US continues to still be in, its also reasonable to see that employment rates have not yet returned to the levels they were at pre-COVID-19. At it's worst, this sharp decline in employment rate was more severe for the employment rate of women compared to the employment rate for men, which properly reflects the findings from our linear probability regression analysis. 

One significant take away from this visual is that females have an employment rate that is higher than the employment rate for males as of January 2021.


#### Marriage Status Analysis  
The second regression analysis was conducted to determine the associated effect being married during the COVID-19 pandemic has on a person's probability of being employed relative to not being married during the COVID-19 pandemic. 
![Marriage Status Analysis](/Images/three.png)

For this regression analysis, what we really want to focus on is the coefficient for the interaction between married and COVID-19 variables in our model as that measures the effect of being married during the COVID-19 pandemic on the probability of being employed relative to not being married.

Prior to the COVID-19 pandemic, we see the effect of being married is associated with approximately 3.41 percentage points higher in the probability of being employed relative to not being married. 

However, once the COVID-19 pandemic started, we see the effect of being married during the COVID-19 pandemic is associated with approximately 2.01 percentage points higher in the probability of being employed relative to not being married during the COVID-19 pandemic.

![Employment by Marriage Status](/Images/four.png)
Figure 2. 

Above in Figure 2 shows that during approximately March of 2020 there is an immediate decline in the employment rate for both married and non-married people resulting from the state mandated stay-at-home orders that were put in place due to the COVID-19 pandemic. 

The employment rate for non-married people can be seen declining to a rate of employment that is much lower than married people at it's worst and the recovery of the employment rate for non-married people still has much has farther to go in order to get back to the pre-COVID non-married person employment rates compared to the employment rate recovery seen for married people, both of which properly reflect the findings from our linear probability regression analysis. 

We can see that from October 2020, the married employment rate is holding steady above the 95% employment rate whereas the not married employment rate has only recovered to an employment rate 90% and seems to be on a more significant downward trend again. It would be interesting to look at non-married people's employment rates over the next few months and a potentially conduct another analysis for this specific concerning trend.  

As of January 2021, this visual shows that the employment rate for married people is higher than the employment rate for non-married people.

#### Age Generation Analysis
The third regression analysis was conducted to determine the associated effect of being in one age generation during the COVID-19 pandemic has on a person's probability of being employed relative to being in another age generation during the COVID-19 pandemic. 
![Age Generation Analysis](/Images/five.png)

For this regression analysis, what we really want to focus on is the coefficient for the interaction between each age generation and COVID-19 variable in our model as that measures the effect of being in one age generation during the COVID-19 pandemic on the probability of being employed relative to being in the Baby Boomer age generation during the pandemic.

Prior to the COVID-19 pandemic, we see the effect of being a person from Generation X is associated with approximately 0.04 percentage points lower in the probability of being employed relative to being in a person from the Baby Boomer generation. 

Prior to the COVID-19 pandemic, we see the effect of being a person from Generation Z is associated with approximately 6.86 percentage points lower in the probability of being employed relative to being in a person from the Baby Boomer generation. 

Prior to the COVID-19 pandemic, we see the effect of being a person from the Millennial generation is associated with approximately 0.96 percentage points lower in the probability of being employed relative to being in a person from the Baby Boomer generation. 

However, once the COVID-19 pandemic started, we see the effect of being a person from Generation X during the COVID-19 pandemic is associated with approximately 0.48 percentage points higher in the probability of being employed relative to being in a person from the Baby Boomer generation. 

Once the COVID-19 pandemic started, we see the effect of being a person from Generation Z during the COVID-19 pandemic is associated with approximately 2.34 percentage points lower in the probability of being employed relative to being in a person from the Baby Boomer generation. 

Once the COVID-19 pandemic started, we see the effect of being a person from the Millennial generation during the COVID-19 pandemic is associated with approximately 0.41 percentage points lower in the probability of being employed relative to being in a person from the Baby Boomer generation. 

![Employment by Age Generation](/Images/six.png)
Figure 3. 

Above in Figure 3 shows that during approximately March of 2020 there is an immediate decline in the employment rate for all age generations of people resulting from the state mandated stay-at-home orders that were put in place due to the COVID-19 pandemic. 

The age group with the most significant employment rate decline during this time was Generation Z and understandably so. In a time where employment rates are dropping, it was difficult for anyone in this group to find a job because nationwide there was a greater rate of people being laid-off than hired. The trend seen in this visual properly reflect the findings from our linear probability regression analysis. 

We also find it relevant to mention that the people who are at the highest risk of developing severe symptoms after contracting the COVID-19 virus are people who fall in the Baby Boomer generation. As such, we find it reasonable to believe that the lower employment rate for people who are from the Baby Boomers generation compared to people from Gen X which can be found in our regression analysis as well as depicted from march onward in this visual is the result of how the COVID-19 virus itself is more severe when contracted by older people rather than younger people.

We can see that from December 2020, the employment rate for people in the Millennial generation seems to be on a more significant downward trend again. This trend is concerning and it would be interesting to keep watching this age generation's employment rates over the next few months.

As of January 2021, this visual shows that the employment rates for Baby Boomers and Generation X are about the same, and the highest, followed by a slight downward trend in the employment rate for Millennials and finally the employment rate for Genz is the lowest.

#### Highest Educational Attainment Analysis
The fourth regression analysis was conducted to determine the associated effect of having one educational attainment level during the COVID-19 pandemic has on a person's probability of being employed relative to having another educational attainment level during the COVID-19 pandemic. 
![Education Analysis](/Images/seven.png)

For this regression analysis, what we really want to focus on is the coefficient for the interaction between each educational attainment category and COVID-19 variable in our model as that measures the effect of having one educational attainment level during the COVID-19 pandemic on the probability of being employed relative to having an Associate degree during the COVID-19 pandemic.

Prior to the COVID-19 pandemic, we see the effect of having below a High School graduate education is associated with approximately 5.44 percentage points lower in the probability of being employed relative to having an Associate degree.

Prior to the COVID-19 pandemic, we see the effect of having a High School graduate education is associated with approximately 1.58 percentage points lower in the probability of being employed relative to having an Associate degree.

Prior to the COVID-19 pandemic, we see the effect of having a Bachelor's degree is associated with approximately 0.40 percentage points higher in the probability of being employed relative to having an Associate degree.

Prior to the COVID-19 pandemic, we see the effect of having Master's degree is associated with approximately 0.71 percentage points higher in the probability of being employed relative to having an Associate degree.

Prior to the COVID-19 pandemic, we see the effect of having a Professional degree is associated with approximately 1.16  percentage points higher in the probability of being employed relative to having an Associate degree.

Prior to the COVID-19 pandemic, we see the effect of having a Doctorate degree is associated with approximately 1.52 percentage points higher in the probability of being employed relative to having an Associate degree.

However, once the COVID-19 pandemic started, we see the effect of having below a High School graduate education is associated with approximately 1.22 percentage points lower in the probability of being employed relative to having an Associate degree during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of having a High School graduate education is associated with approximately 0.96 percentage points lower in the probability of being employed relative to having an Associate degree during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of having a Bachelor's degree is associated with approximately 1.12 percentage points higher in the probability of being employed relative to having an Associate degree during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of having Master's degree is associated with approximately 2.65 percentage points higher in the probability of being employed relative to having an Associate degree during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of having a Professional degree is associated with approximately 3.25 percentage points higher in the probability of being employed relative to having an Associate degree during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of having a Doctorate degree is associated with approximately 2.65 percentage points higher in the probability of being employed relative to having an Associate degree during the COVID-19 pandemic.

![Employment by Educational Attainment](/Images/eight.png)
Figure 4. 

Above in Figure 4 during approximately March of 2020, you will see an immediate decline in the employment rate for all people regardless of education level, this drop is the result of state mandated stay-at-home orders that were put in place due to the COVID-19 pandemic. 

Since the beginnings of quarantine, employment rates have gone up but given the continued pandemic-induced State of Emergency that the US continues to still be in, its also reasonable to see that employment rates have not yet returned to the levels they were at pre-COVID-19. At it's worst, this sharp decline in employment rate was more severe for the employment rate of women compared to the employment rate for men, which properly reflects the findings from our linear probability regression analysis. We can see from Figure 4 that the group with below a high school degree, as of October 2020 the employment rate for this group has been on a steady decline.


#### Racial Category Analysis
The fifth and final regression analysis was conducted to determine the effect being one race during the COVID-19 pandemic has on a person's probability of being employed relative to having another race during the COVID-19 pandemic. 
![Racial Category Analysis](/Images/nine.png)

For this regression analysis, what we really want to focus on is the coefficient for the interaction between each race and COVID-19 variable in our model as that measures the effect of one race during the COVID-19 pandemic on the probability of being employed relative to being American Indian/ Aleut/ or Eskimo.

Prior to the COVID-19 pandemic, we see the effect of being Asian is associated with approximately 5.5 percentage points higher in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo.

Prior to the COVID-19 pandemic, we see the effect of being Black is associated with approximately 1.76 percentage points higher in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo.

Prior to the COVID-19 pandemic, we see the effect of being Hawaiian/Pacific Islander is associated with approximately 4.68  percentage points higher in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo.

Prior to the COVID-19 pandemic, we see the effect of being Mixed races is associated with approximately 2.68 percentage points higher in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo.

Prior to the COVID-19 pandemic, we see the effect of being White is associated with approximately 4.94 percentage points higher in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo.

However, once the COVID-19 pandemic started, we see the effect of being Asian is associated with approximately 2.13 percentage points lower in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of being Black is associated with approximately 0.49 percentage points lower in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of being Hawaiian/ Pacific Islander is associated with approximately 3.03 percentage points lower in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of being Mixed races is associated with approximately 2.04  percentage points lower in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo during the COVID-19 pandemic.

Once the COVID-19 pandemic started, we see the effect of being White is associated with approximately 0.81 percentage points higher in the probability of being employed relative to being American Indian/ Aleut/ or Eskimo during the COVID-19 pandemic.

![Employment by Racial Category](/Images/ten.png)
Figure 5. 

Above in Figure 5, when quarantine started due to COVID-19 in the US, which was in March 2020, there is an immediate decline in employment between individuals of all racial backgrounds. The hardest hit group were individuals with an American Indian/ Aleut/ and Eskimo background. With the latest 2021 data, it looks like racially, all the different groups are around the same employment rate, ranging between .85 and .95. 


# Assumption Acknowledgement
The linear probability regression model used for each regression model of our analysis assumes that the probability of our outcome is a linear function of the regressors, when in reality we must acknowledge that the true relationship between a binary outcome, in our case: being employed or not being employed, and the binary or categorical explanatory variable used in our models as the variable of interest are going to have an inherently nonlinear relationship. In an effort to best accommodate this assumption violation, we have provided supplemental visuals where employment rate is being used as a substitute for the employed outcome variable in our linear probability regression models.

Gender Analysis:
One assumption for this analysis is that people can only be a gender of male or female. There was no data collected for people who identify as non-binary or any other sexual orientation in the IPUMS CPA data, so there would have been means for us to account for those respondents who identify as anything other than male or female in this analysis.

Marriage Status Analysis:
We grouped people who are married, but do not live with their spouse under the classification of not being married. This might have been an erroneous assignment on our part, but it was our assumption that people who are living in other homes separately but married might have a spouse in another country and are otherwise living as a single person. From this analysis we wanted to determine if people who are married, in the traditional sense, were more impacted by COVID-19 than single people in regard to their employment status and so we categorized people who are married but living separately accordingly.

Age Generation Analysis:
Another assumption we made was that people who are employed are actually people who are working in the traditional sense, but there could be plenty of older people included in our data set whose employment status was not affected by the COVID-19 pandemic because they are working by title alone. By this there could be people who are owners or presidents of companies who do not have an active day-to-day role in the operations of the business and would not be laid off even if layoffs were occuring at their company because they hold such a valuable, high up position in the company.

Another assumption we made for this analysis was that everyone in each generation is the same. By categorizing individuals into their respective age generation category, we may have failed to account for the nuanced, yearly age level effects this pandemic may have had on the employment status for people with different inner-group ages.

Highest Educational Attainment Analysis:
Similar to the second assumption for Age, we grouped highest educational attainment into six separate buckets when the original IPUMS CPA data extract had 18 uniquely coded values for different levels of educational attainment. By grouping educational attainment as we have, we may have missed out on the nuanced, individual education level effects this pandemic may have had on the employment status for people with different inner-group education levels.

Racial Category Analysis:
Finally, for the racial category analysis, we made the same grouped assumption as the previous analysis where we bucketed anyone who identified as more than one unique racial group in their response for the "race" variable in the IPUMS CPA data into a "Mixed" race category. By doing this we once again may have missed out on the nuanced, individual multi-race level effects this pandemic may have had on the employment status for people who are different inner-group races.

# General Answer to "Who has money to spend?"
Briefly stated, on average as of 2021 the following are our conclusions: 
1) Women are working more than men.

2) Married people are working more than non-married people. 

3) Baby Boomers and Generation X working more than Millennials, but Millennials are working more Generation Z. 

4) People with Doctorate or Professional degrees are working more than people with Master's degrees. 
People with Master’s degrees are working more than people with Bachelor's degrees. 
People with Bachelor’s degrees are working more than people with Associates degree. 
People who have Associates degrees are working more than High School graduates. 
People who graduated High School are working more than people with below a High School graduate degree.

5) White people are working more than Asian people.
Asian people are working more than Hawaiian/ Pacific Islanders, Black people, and people with a Mixed race.
American Indian/Aleut/Eskimo people are working the least.

We found supporting evidence for each of these claims as shown in Figures 1 - 5 above showing average employment rates per grouping for each of the demographic variables evaluated in this analysis.

# General Answer to "What has changed about who is working and earning money?"
On average, over the year preceding February 2020 the following are our conclusions: 

1. Women have historically been more likely to be employed than men, but employment rate trends show that this claim is true at times, but not always true. The employment rate for women can be seen occasionally dipping below the employment rate for men. 

The biggest change is that employment rates for both women and men have not recovered to pre-pandemic employment rate levels.

2. Married people have historically been more likely to be employed than non-married people, so nothing has changed in that regard and employment rate trends support this claim. 

The biggest change here is that employment rates for both married and not married people have not recovered to pre-pandemic employment rate levels.

3. Baby Boomers and Gen X have historically been more likely to be employed than Millennials who have historically been more likely to be employed than Gen Z. Employment rate trends support this claim. 

The biggest change here is that employment rates across all groups have not recovered to pre-pandemic employment rate levels.

4. Historically, the higher educational attainment an individual has achieved, the more likely they are to be employed, so there is no change in that regard and employment rate trends support this this claim. 

The biggest change here is that employment rates across all levels of educational attainment have not recovered to pre-pandemic employment rate levels.

5. Historically, being Asian had the highest probability of being employed compared to all other racial categories pre-pandemic followed by Hawaiian/Pacific Islanders and then White people. However, this has changed as now being White has a higher probability than people who are Asian to be employed. Employment rate trends support this claim. 

Another change observed here is that employment rates across all racial categories have not recovered to pre-pandemic employment rate levels.

