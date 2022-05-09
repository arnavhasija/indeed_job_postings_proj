# indeed_job_postings_proj
Data Science job postings in three cities (Toronto, New York City, and San Francisco) were scraped from Indeed and analyzed to compare job markets and determine highly valued skills.

Below are the some of the questions I wanted to address in the analysis:
- What are the top skills employers are currently looking for?
- Are certain companies or types of companies/industries posting more data science related jobs?
- Are job titles an accurate representation of what the job description/skills summary states?
- Analysis by job locations - how many roles are now remote vs in the office?
- How many years of industry experience are jobs typically looking for?
- What tools are the most commonly asked for in the postings?
- Are US based companies in NYC or SF, also hiring in Toronto?


<b>Topic Modelling</b>

NMF (Non-negative matrix factorization) was used to perform topic modelling using the keywords parsed from the job description field.

First the job_descriptions were converted to a matrix of TF-IDF features. 

When using NMF, 6 topics were chosen after seeing an overlap in the topics/areas asked for in the job desciptions when a greater number of topics were chosen as the input parameter (n_components).

After fitting the model to the job description field, top 15 topics were analyzed for each topic as shown in image below.

First topic had keywords such as architecture, management, governance, etc. in and was therefore labeled as Data Management and Engineering.
Second topic had keywords such as bachelor, statistics, degree, etc. and was therefore labeled as Stats/CS background.
Third topic had terms such as algorithms, models, machine learning, and was thus assigned a label of ML algorithms and models.

Similarly, labels for other topics were assigned based on the top 15 words for each topic (shown below).

![](/images/topics_list.JPG)

It was found that Data Management and Engineering was among the top skills being required in Toronto for data science jobs. Managing data science teams and working 
with big data and cloud were also frequently asked for in the job descriptions.

![](/images/topic_labels_frequency_Toronto.JPG)

<b>Data Sciences jobs in Toronto by companies</b>

Companies such as Wayfair, Deloitte, and Bell Canada currently have the most number of job postings for data science roles. 

![](/images/Toronto_most_jobs_by_companies.JPG)

In Wayfair, most roles are related to managing data science teams followed by experience with EDA and segmentation.
Deloitte, Bell, TD, and RBC are looking for Data Management and Engineering experience for a number of roles.
Skills in big data and cloud/distributed computing are also asked for in quite a few postings for Deloitte. 

![](/images/Toronto_jobs_by_companies_topic_label.JPG)

<b>Are job titles an accurate representation of what the job description/skills summary states?</b>

Association rules mining was used to determine if a job title accurately represents the nature of the role. Since data science is a such a broad profession, the skills 
required for each job tend to vary significantly.

First, I checked for the frequency of jobs by their titles to check the most popular job titles. 

As expected, most popular titles were Data Scientist, Senior Data Analyst, and Senior Data Scientist.

Data Scientist job title and ML algorithms and models had a lift of 1.66. 

This means that typically there is a high association between the two. Job descriptions with a title Data Scientist,  will likely have a high propensity to ask for skills in machine learning algorithms and models.

For a Senior Data Scientist role, having a Stats/CS background had the highest lift of 1.84 followed by Managing data science teams with a lift of 1.43.

While for a ML Engineer role, ML algorithms and models had the highest lift of 3.2. 


<b>Analysis by job locations - how many roles are now remote vs in office?</b>

Around 28% of the data science jobs in Toronto are either fully remote or remote/hybrid currently, while 72% are in the office.

![](/images/remote_jobs_in_Toronto.JPG)

In comparison, 32.6% of jobs in New York city are remote or hybrid remote.

![](/images/remote_jobs_in_New_York.JPG)

The fraction is a lot higher for San Francisco jobs as about 50% of the roles are remote/hybrid remote. This could also be due to a smaller number of data science job postings that were scraped for San Francisco.

![](/images/remote_jobs_in_SF.JPG)

<b>What skills/experience is most commonly asked for in data science job postings?</b>

The word cloud below shows some of skills that are most commonly asked for in the job description of each role.

![](/images/word_cloud.JPG)

The analysis was performed on all the data combined for Toronto, New York City, and San Francisco. 

Machine Learning, business analysis, and data engineering were among the top skills being asked for in the postings. While many postings also ask for skills in data 
visualization, building data pipelines, and management of teams.

In terms of education, most jobs ask for a master's degree, followed by a bachelor's degree in a quantitative field. While there were a few postings that listed having
a PhD as a requirement as well.

![](/images/jobs_education_level.JPG)


<b>Are US based companies in NYC or SF, also hiring in Toronto?</b>

Quite a few US based companies such as Tonal, Citi, Pinterest, etc. are hiring currently in Canada.

![](/images/us_based_companies_in_Canada.JPG)
