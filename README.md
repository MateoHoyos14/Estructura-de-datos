# The Analysis

## 1. What are the most demandes skills for the top 3 most popular data roles?

To find the most demanded skills for the top 3
most popular data roles. I filtered out those ositions y which ones were the most popular, and got the top 5 skills for these top 3 roles. This query highlights the most popular job titles and their top skills, showing which skills I should pay attention to depending on the role I'm targeting

View my notebook with detailed steps here:
[2_Skills.ipynb](3_Project\2_Skills.ipynb)

### Visualize Data
```python 
for i, job_title in enumerate(job_titles):
    df_plot = df_skills_perc[df_skills_perc['job_title_short'] == job_title].head()
    # df_plot.plot(kind='barh', x='job_skills', y='skill_percent', ax=ax[i], title=job_title)
    
    sns.barplot(data=df_plot,x= 'skill_percent', y='job_skills', ax=ax[i], hue='skill_count', palette='dark:b_r')
```

### Results
![Visualization of Top Skills for Knowledge](3_Project\images\skill_demands_all_data_roles.png)


### Insights

- Python is a versatile skill, highly demanded across all
three roles, but most prominently for Data Scientists (72%) and Data Engineers (65%).

- SQL is the most requested skill for Data Analysts and
Data Scientists, with it in over half the job postings for both roles.
For data Engineers, Python is the mooost sought-after skill, appearing in
68% oof job postings.

- Data Enaineers require more specialized technical skills (AWS. Azure. Soark) compared to
Data Analysts and Data Scientists who are expected to be proficient in more qeneral data management
and analvsis tools (Excel. Tableau).



# The Analysis
## 2. How are in-demand skills trending for Data Analysts?

### Visualize Data
```python 
from matplotlib.ticker import PercentFormatter

df_plot  = df_DA_US_percent.iloc[:, :5]
sns.lineplot(data=df_plot, dashes=False, palette='tab10', legend='full')

plt.gca().yaxis.set_major_formatter(PercentFormatter(decimals=0))

plt.show()
```

### Results
![Trending Top Skills for Data Analyst in the US](3_Project\images\skill_trend_DA.png)
*Bar graph visualizing the trending top skills for data
analysts in the US in 2023.

### Insights:

- SQL remains the most consistently demanded skill
throughout the year, although it shows a gradual
decrease in demand.
- Excel experienced a significant increase in
demand starting around September, surpassing both
Python and Tableau by the end of the year.
- Both Python and Tableau show relatively stable
demand throughout the year with some fluctuations
but remain essential skills for data analysts. Power Bl,
hile less demanded compared to the others, shows a slight upward trend towars the year's end.


## 3. How well do jobs and skills pay for Data Analysts?

### Salary Analysis
```python 

sns.boxplot(data=df_US_top6, x='salary_year_avg', y='job_title_short', order=job_order)

ticks_x= plt.FuncFormatter(lambda y, pos:f'{int (y/ 100)}K')

plt.gca().xaxis.set_major_formatter(ticks_x)

plt.show()

```

#### Results

![Salary Distributions of Data Jobs in the US](3_Project\images\salary_boxplot.png)

*Box plot visualizing the salary distributions for the top 6 data job titles.*

#### Insights
- There's a significant variation in salary ranges across different job titles. Senior Data Scientist positions tend to have the highest salary potential, with up to $600K, indicating the high value placed on advanced data skills and experience in the industry.

- Senior Data Engineer and Senior Data Scientist roles show a considerable number of outliers on the higher end of the salary spectrum, suggesting that exceptional skills or circumstances can lead to high pay in these roles. In contrast, Data Analyst roles demonstrate more consistency in salary, with fewer outliers.

- The median salaries increase with the seniority and specialization of the roles. Senior roles (Senior Data Scientist, Senior Data Engineer) not only have higher median salaries but also larger differences in typical
salaries, reflecting greater variance in compensation as responsibilities increase.

# The Analysis
## 3. How wett do jobs and skills pay for Data
### Highest Paid & Most Demanded Skills for Data Analysts


#### Visualize Data
``` python
fig, ax= plt.subplots(2,1)

# Top 10 Highest Paid Skills for Data Analysts

sns.barplot(data= df_DA_top_pay, x='median', y=df_DA_top_pay.index, hue='median', palette='dark:b_r')

# Top 10 Most In—Demand Skills for Data Analysts

sns.barplot(data= df_DA_skills, x='median', y=df_DA_skills.index, hue='median', palette='light:b')

plt.show()
```


![The Highest Paid & Most In-Demand Skills for Data Analysts in the US](3_Project\images\highest_paid_and_most_in_demand_skills_for_DA_US.png)

*Two separate bar graphs visualizing the highest paid skillss and most in—demand skills for data analysts in the US.*

#### Insights:

- The top graph shows specialized technical skills like `dplyr`, `Bitbucker`, and `gitlab` are associated with higher salaries, some reaching up to $200K, suggesting that advanced technical proficiency can increase earning potential.

- The bottom graph highlights that foundational
skills like `Excel` , `PowerPoint` , and `SQL` are he most in—demand, even though they may not offer he highest salaries. This demonstrates the portance of these core skills for employability n data analysis rotes.

-There's a clear distinction between the skills that are
ighest paid and those that are most in-demand.
ata analysts aiming to maximize their career
otential should consider developing a diverse skill
et that includes both high-paying specialized skills
nd widely demanded foundational skills.
