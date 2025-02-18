# Project summary 

Full presentation of the project at:

[ - Link to Portfolio - ](https://max0513.github.io/2025/02/01/Saliford-turn-over-analysis.html)

## Context  

<br>

Saliford Motors has noticed a high turnover rate from their work force. They ask for a machine learning algorithm [ML] that would help them screen for possible departures in their work force based on data they collected from their employees, past and present. If succesful, the ML model could give Saliford an opportunity for action in preventing the departure before it takes place. 

An initial EDA using `python` revealed key insights as to where company leadership could further investigate to hopefully reveal the exact causes of departure.

A Tree Based Classification model with an f1 accuracy score of about 94% was then computed to help screen employees for potential risk of leaving Saliford, based on different metrics collected by the company.

<br>

## Data  <a name="overview-data"></a>

<br>


*The data contained 14999 entries of which 3008 rows where duplicates. Most ouliers present were found in the year_spent_company column (6.87% of values).* 
    
*Most relevant correlations found were between **number_project and average_montly_hours** and between **satisfaction_level and left**.*
    
*16.6% of data is categorised as **left** so the dataset is moderatly imbalanced.*
  
*EDA revealed no clear non-sensical data present.*

<br>

<br>

<br>

**satisfaction_level (int)** : Self-reported satisfaction of employee

**last_evaluation (int64)** : Score of employee's last performance review

**number_project (int64)** : Number of projects contributed in the last year

**average_montly_hours (int64)** : Average hours worked by month in the last year

**time_spent_company (int64)** : Number of years employee has been working at Saliford Motors

**work_accident (int64)** : Whether employee has been involved in a work accident [1] or not [0]

**left (int64)** : Whether employee is still employed at Saliford [0] or has left [1]

**promotion_last_5years (int64)** : Whether employee got promoted in the last 5 years

**department (str)** : Employee's department

**salary (str)** : Whether employee's salary is considered 'high', 'medium' or 'low' based on undefined numbers

<br>