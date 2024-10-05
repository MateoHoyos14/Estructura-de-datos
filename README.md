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
