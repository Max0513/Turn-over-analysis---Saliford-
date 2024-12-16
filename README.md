
# Project summary
This project is a fictive analysis based on data provided by Kaggles.com.

The mandate is to generate insight on the high turnover rate of Saliford Motor based on a company survey containing 11991 non-null, non-duplicated entries figuring 10 columns of data each. 
```
Note: View data dictionary for more information on different metrics used in the analysis
```
An initial EDA reveiled key insights as to where company leadership could further the investigation in hopes to reveal the exact cause of the departures.

A prediction model was then computed to help screen employees for potential risk of leaving Saliford, based on different metrics collected by the company.

## Business takeaways 

Data exploration revealed valuable insights about Saliford's work force:

Following charts show how the Monthly hours worked by saliford's employees relate to their tenure.

<img src="Notebooks/average_monthly_hours_distribution.png" width=40% height=40%> <img src="Notebooks/average_hours_per_number_project.png" width=40% height=40%>

```
Burn out looks to be a significant factor in departures
```
- Employees working outside of the 160 to 210 hours a month range are at much higher risk of turnover, the average in the US being 176

- 100% of workers assigned 7 projects left the company, dropping to 45% when assigned 6
Regardless of number of projects assigned departures seem to be correlated to the time requiered by those project rather than to the projects themselves


```
3 departments stand out from the rest and would require further investigation
```
The chart below shows percent of departure by departement.

<img src="Notebooks/departures_per_department.png" width=40% height=40%>


```
The promotions system does not look ideal for retention
```
- 98.3% of workers did not receive a promotion in the last 5 years
- 
```
Work accidents
```
```
Last evaluation
```
```
Satisfaction
```
- The third and fourth years seem to be a turning point in satisfaction levels 
## Presentation of the  model


## Chalenges
```
This project was my first experience with version control as well as in a multiple folder project that needs interaction between multiple files
```
- I had to figure out a clear organisation method to present the project. I settled on the cookiecutter data template that I adapted to my needs
- I lost a day of work due to forgetting to commit progress, had to learn the hard way to never do that again.
## Next step


## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── README.md          <- The top-level README for developers using this project
├── data
│   ├── interim        <- Intermediate data that has been transformed
│   └── raw            <- The original, immutable data dump
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`
│
├── references         <- Data dictionary
│
└─ reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    └── figures        <- Generated graphics and figures to be used in reporting