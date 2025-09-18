# My Analysis

## Chapter 1: What are the most demanded skills for the top 3 most popular data roles?
To find the most demanded skills for the top 3 most popular data roles, I filtered out those positions by which ones were the most popular, and got the top 5 skills for these top 3 roles. This query highlights the most popular job titles and their top skills, showing which skills I should pay attention to depending on the role I'm targeting.

View my notebook with detailed steps here:
[2_skills_count.ipynb](Project/2_skills_count.ipynb)

### Visualize Data

```python
fig, ax = plt.subplots(len(job_titles), 1)

for i, job_title in enumerate(job_titles):
    df_plot = df_skills_perc[df_skills_perc['job_title_short'] == job_title].head(5)[::-1]
    sns.barplot(data=df_plot, x='skill_percent', y='job_skills', ax=ax[i], hue='skill_count', palette='dark:b_r')

plt.show()
```

### Results

[Visualization of Top Skills for Data Nerds](Project/images/skills_percent.png)

## Strategic Skill Development Recommendation
Aspiring professionals should prioritize SQL and Python regardless of specialization

Career pivots between roles require targeted skill acquisition in domain-specific tools

Organizations should structure teams to leverage these complementary skill sets

Training programs should emphasize both universal and role-specific technologies

## Chapter 2: How are in-demand skills for data analysts

View my notebook with detailed steps here : [3_skills_trend.ipynb](Project/3_skills_trend.ipynb)

```python
df_plot = df_DA_US_percent.iloc[:, 1:6]

sns.lineplot(data = df_plot,dashes = False,legend = True)
sns.despine()
```

### Results

[Trending Top Skills for Data Analysts](Project/images/skills_trend.png)

## Insights

SQL consistently led the demand across all months, highlighting its critical role in data management and analysis.
Its dominance shows that SQL remains the foundation of data-related work despite the rise of newer tools.

Excel stayed ahead of Python and Tableau, proving its widespread use across industries.
Its versatility in reporting, organization, and day-to-day analysis keeps it highly relevant.

Python and Tableau maintained stable demand throughout the year without major fluctuations.
Their steady usage reflects continued trust in Python for analytics and Tableau for visualization.

SAS had the lowest demand among all tools, showing a decline in preference.
The shift suggests organizations are favoring open-source and more flexible alternatives.

## Chapter 3 Highest Paid and Most Demanded Skills for Data Analytics

View my notebook with detailed steps here : [4_Salary_Analysis.ipynb](Project/4_Salary_Analysis.ipynb)

### Visualize Data

```python
fig,ax = plt.subplots(2,1)

sns.set_theme(style = 'ticks')

sns.barplot(data = df_DA_top_pay,x = 'median',y=df_DA_top_pay.index,hue = 'median',ax = ax[0],palette = 'dark:b_r')

ax[0].set_title('Top 10 highest Paid Skills for Data Analysts')

sns.barplot(data = df_DA_skills,x = 'median',y = df_DA_skills.index,hue ='median',ax=ax[1],palette = 'light:b')
ax[1].set_title('Top 10 Most In-Demand Skills for Data Analysts')

plt.tight_layout(h_pad= 0.7)
```

[Visualization of Highest Paid and Demanded Skills](Project/images/Highest_Paid_Demanded_Skills.png)

## Insights 

- Top Graph shows that skills such as 'dplyr', 'bitbucket' and 'gitlab' are associated with highest salaries. Some of them even touched 200K. Developing these skills can increase earning potential.

- Bottom graph shows foundational skills such as 'SQL', 'Python' and 'R' are most in demand skills although they do not offer highest of salaries

- There is clear distinction between highest paid and most demanded skills. Diverse skill set are important to find roles in data analytics.
