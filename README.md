
# Project summary
This project is a fictive analysis based on data provided by Kaggles.com, originating from the google career certificate for data analysis.

The mandate is to generate insight on the high turnover rate of Saliford Motor based on a company survey containing 11991 non-null, non-duplicated entries figuring 10 columns of data each. 

`The project resulted on valuable insights on the data for the stakeholders to reflect upon as well as in a **Tree based classification model** with a prediction f1 score of about **94%**.`
```
Notes: 

- View data dictionary in references folder for more information on the different metrics used in the analysis.

- A folder structure template is also available at the end of this readme.
```
## Process

An initial EDA using `python` reveiled key insights as to where company leadership could further the investigation in hopes to reveal the exact cause of the departures.

A prediction model was then computed to help screen employees for potential risk of leaving Saliford, based on different metrics collected by the company.

## Summary of EDA

- Satisfaction is the greater influencer in the outcome variable.
- High work hours (Above 220 hours a month) increase the risk of departure.
- The promotion system of *Saliford* might contribute to higher turnover.
- 3 to 5 project count looks to be ideal for retention.
- Years 4 and 5 need further investigation over the satisfaction level decrease in the work force.

## Business takeaways 

Data exploration revealed valuable insights about Saliford's work force:

*Following charts show how the **Monthly hours** worked by saliford's employees relate to their **tenure**.*
<div style="border: 2px solid black;">
<p align="center">
<img src="reports/figures/distribution_of_monthly_hours_average.png" width=49% height=40%> <img src="reports/figures/monthly_hours_per_project.png" width=49% height=40%>
</p>

```
Insight 1 : Burn out looks to be a significant factor in departures
```
- Employees working outside of the `160 to 220 hours a month` range are at much higher risk of turnover, the average in the US being 176. A recommended maximum for monthly hours could be set to 220 hours to help this issue.

- 100% of workers assigned **7 projects** left the company, dropping to 45% when assigned 6.

- Regardless of number of projects assigned, departures seem to be correlated to the time requiered by those project rather than to the projects themselves.



```
Insight 2 : three departments stand out from the rest and would require further investigation
```
*The chart below shows **percent of departure** by departement.*

<img src="reports/figures/departure_by_department.png" width=49% height=40%>


```
Insight 3 : The promotions system does not look ideal for retention.
```
- **98.3%** of workers `did not receive a promotion` in the last 5 years.
- Around `17% of employees who did not receive a promotion in the last 5 years departed`, dropping to 4% if they did.
- Implementing a structure with more echelon could be a consideration to add a sense of progression in the work force.
- The `number of promotions` do not appear related to the **number of hours worked**, **the number of project participated in** nor to the **last evaluation of the worker**. They do however, appear to be correlated to their **satisfaction levels**. *(View EDA for further details)*
```
Insight 4 : Aiming for 3 to 5 projects per employee could help lower departures.
```

<img src="reports/figures/table_departure_per_years.png" >

- It is worth noting that as stated before, the **time spent working on project** seems a more likely indicator that the **number of project**.

- Increasing project number does however correlate to an increase in monthly hours worked.

```
Insight 5 : Satisfaction levels are dipping in the four year category.
```
 **50%** of the company repports a **satisfaction level above 0.66** with **37% at or above 0.75** wich is not bad but `levels drop around the 4 years mark`.
<p align="center">
<img src="reports/figures/table_satisfaction_by_year.png" width=25%> <img src="reports/figures/satisfaction_per_years_at_company.png" width=73% height=40%>
</p>

- Regardless of departure, `satisfaction levels drop at the 4 years employement mark`.
- Satisfaction of departed personnel follows a downward trend until year 5 and then picks back up at year 5, suggesting that those that leave for satisfaction reasons might mostly do so by year 4. Suggesting departures in year 5 and 6 might be due to other reasons.

*Chart below shows **departures** tend to follow the trend in **satisfaction levels** drop. `Years 4 and 5 have the highest turnover rates`.*

<img src="reports/figures/leave_per_years_at_company.png" width=49% height=40%>

```
Insight 6 : We can speculate on possible reasons for leaving using data from scatter chart.
```
*Scatter chart below shows 3 distinct areas of departures:*

<img src="reports/figures/scatter_plot_satisfaction_vs_hours.png" width=49% height=40%>

- *High work hours, low satisfaction*: Most likely left from **burn out**.
- *High work hours, high satisfaction*: Most likely left **for higher paid job**.
- *Low work hours, low satisfaction*: Most likely fired for **low performance**. 

## Presentation of the  model

The chosen model is the `Tree based machine learning model`.

- The requiered task is **classification**.

- EDA revealed a fair proportion of relevant **outliers** so we need an outlier resilient model.

- Logistic regression fits requierements, but it seems the tree model could add valuable insights to stakeholder by studying the branches, it then seems like a good first choice in a world where making both and comparing would require too much time.

### Model score


*A model with the following parameters and scores was selected for use, selecting the f1 score as the best predictor score.*

<img src="reports/figures/model_results_table.png" width=100% height=40%>

Using 3598 data point *(About 30% of the data)* as test_data, we could predict departure with an `f1 score of about 94%`.

*The following **Confusion matrix** show the repartition of the 3598 predicted data points*

<img src="reports/figures/confusion_matrix.png" width=49% height=40%>

- `Yellow` top/left box shows retained employees that where **correctly predicted** as such.
- `Light Purple` bottom/right box shows departed employees that were **correctly identified**.
- `Bright Purple` Boxes show **incorrectly identified** data. 
### Model results

In a tree based model, gini importance more or less refers to the degree to wich the metric influences the classification of the model.

*The graph below shows metrics graphed by gini importance*.

<img src="reports/figures/gini_importance.png" width=49% height=40%>

- Once again we see another example of the effect of satisfaction level over the turn over rate.


## Chalenges and what I would do differently
```
This project was my first experience with version control as well as working in a multiple folder project with interaction between multiple folders
```
- I had to figure out a clear organisation method to present the project. I settled on the cookiecutter data template that I adapted to my needs
- I lost a day of work due to forgetting to commit progress, had to learn the hard way to allways backup and update files.

## Next steps for the project
```
Deploy the model on streamlit for ease of acces.
```

```
 Investigate the three areas from the scatter chart further .
```
- Investigate performance statistics for employees between 0.3 and 0.5 in satisfaction_levels that are also in the 125 to 175 average_montly_hours range to confirm hypothesis about possible layoff due to low performance.
- Investigate salary and promotion metrics for employees between 0.75 and 1 satisfaction_levels that also fit the 225 hours and more category to confirm hypothesis about the group leaving for a higher paid job due to lack of advancement.
- Run EDA over the new dataframes created by the filtering of the three target zones to see if they behave differently.
```
 Construct a logistic regression model to compare for better prediction score with the tree model if time permits.
```
```
 Get access to higher quality data.
```
- Year since promotion would be better than promotion in last 5 years
- distinction between layoff and resignation.
- male / female category could had further insights to the EDA as well as shed light on possible discrimination in the present or future.
- age column is a relevant information to work with.
- distance from home could had valuable insights to the data.
- salary column could have a higher level of detail for more control, there is no way to know what a 'High' salary is currently.
```
 Generate dashboards for management to better track important metrics.
```
- Machine learning models can be a good tool, but an imperfect tool. Management must be equipped with good good data tools to add human insight wich is as much valuable to solving problems.

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