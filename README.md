![Ironhack logo](https://i.imgur.com/1QgrNNw.png)

# DonorsChoose | Data Analysis Project

## Project Description:

Final Ironhack project.

The purpose of this project is to gain insights into Project Funding Success based on projects listed on [DonorsChoose.org](https://www.donorschoose.org/) 

DonorsChoose.org partnered with Google.org and shared this [Data](https://www.kaggle.com/donorschoose/io) on Kaggle as an invitation to help them "pair up donors to the classroom requests that will most motivate them to make an additional gift. To support this challenge, DonorsChoose.org has supplied anonymized data on donor giving from the past five years. The winning methods will be implemented in DonorsChoose.org email marketing campaigns."

While the aim of this project differs from the original challenge, the data lends itself well to my own purposes. 

### Process:

1. Checked each individual csv for duplicates and mistakes before merging. Donation ID (in `donations.csv`) and Project ID (in `projects.csv`) both contained duplicates. 
    A. In the case of donations, the date received was the difference for each duplicate pair. The 'bad' duplicate had copied the 'project fully funded' date in the 'donation received date' instead. 
    B. In the case of duplicate Project ID's, the same project was listed under two separate project types (teacher led/professional development). These could be inferred from the Project essays and needs statements.

2. Merged the data and filtered on California; the dataframe was way too large for the timeframe and resources that I had to work with. California had the most projects as well as the most donors. 

3. Further cleaning and making the dataframe model-ready (eliminating or encoding categorical data)

4. Building and testing three ML models: Random Forest Regression, K-nearest-Neighbors, and Logistic Regression. 
    A. I worked with these three models using three 'iterations' of my data:
        1. Mostly categorical data without using the k-1 method (dropping the first layer)
        2. The same as the former, but then using `drop_first=True` for dummies
        3. Using intuition and an exploration of the data, dropping three columns that corresponded to one feature (teacher's gender). The latter proved most effective in making the models work. 


### Further work:

1. NLP for project essays and needs statements could be interesting. See if there is correlation between length/tone of essay (using sentiment analysis, perhaps, or a version of it). 

2. Working out the Classification model K-nearest neighbors to see the result of what makes a project successful in reaching its funding goal. I spent most of my time cleaning and analysing the data, and finally building the models. 


### On Project Status fields:

These fields provide status information and dates for when a project reached their milestones. Dates will be null if the project did not reach that particular milestone. For example, if a project was posted but not completed, the date_completed would be null while the date_posted would have a date.

funding_status refers to the status of this project as of the date the dataset was created. Reallocated projects are projects that received partial funding but the project never completed, so the donations were moved towards another project. Completed projects refer to projects that received full funding. Expired projects are ones that expired before donations were made. Live projects are projects that were still open for donations on the day the dataset was created.

funding_status: Completed, Expired, Live, or Reallocated
date_posted: Date a project was approved by staff to be listed on the site
date_completed: Date a project become fully funded
date_expiration: Date the project was set to expire and be delisted from the site

[Source](https://research.donorschoose.org/t/opedata-layout-and-docs/18)


### On using Free Lunch as proxy for poverty in a given school:

"The percentage of students receiving free or reduced price lunch is often used as a proxy measure for the percentage of students living in poverty. While the percentage of students receiving free or reduced price lunch can provide some information about relative poverty, it should not be confused with the actual percentage of students in poverty enrolled in school.

...

Despite its limitations, the free/reduced price lunch data are frequently used by education researchers as a proxy for school poverty since this count is generally available at the school level, while the poverty rate is typically not available. Because the free/reduced price lunch eligibility is derived from the federal poverty level, and therefore highly related to it, the free/reduced price lunch percentage is useful to researchers from an analytic perspective."

[Source: NCES Blog](https://nces.ed.gov/blogs/nces/post/free-or-reduced-price-lunch-a-proxy-for-poverty)

For current purposes, I can justify using the data as a proxy, mainly because DonorsChoose does so on its dashboard for users who are choosing a project to fund.


### Codebook:

`donations.csv`

For every project in the Projects.csv dataset, there are one or more donations. This dataset contains each donation from a citizen donor and is joined with the dataset above using the “Project ID” column.testt test1

**Project ID** Unique ID of a project<br>
**Donation ID** Unique ID of a donation<br>
**Donor ID** Unique ID of a donor<br>
**Donation Included Optional** DonationYes/No to give 15% of donation amount to Donoschoose<br>
**Donation Amount** Total amount donated for a project<br>
**Donor Cart Sequence** Project position on list of desired donations within Cart list.<br>
**Donation Received Date** Date and time on which the donation was recieved<br>

`donors.csv`

For every project in the Projects.csv dataset, there are one or more donations. This dataset contains each donation from a citizen donor and is joined with the dataset above using the “Project ID” column.testt test1

**Donor ID** Unique identifier of a donor.<br>
**Donor City** The donor’s city.<br>
**Donor State** The donor’s state.<br>
**Donor Is Teacher** Whether or not the donor is also a teacher with a DonorsChoose.org teacher account.<br>
**Donor Zip** The donor’s zip code (only first 3 digits).<br>

`projects.csv`

For every project in the Projects.csv dataset, there are one or more donations. This dataset contains each donation from a citizen donor and is joined with the dataset above using the “Project ID” column.testt test1

**Project ID:** Unique identifier of a project.<br>
**School ID:** Unique identifier of a school where the project is proposed from.<br>
**Teacher ID:** Unique identifier of a teacher who proposed the project.<br>
**Teacher Project Posted Sequence:** Represents the order as a project issued by the teacher.<br>
**Project Type:** Type of the project.<br>
**Project Title:** Title of the project.<br>
**Project Essay:** Essay of the project.<br>
**Project Short Description:** Description of the project.<br>
**Project Need Statement:** Statement for the resources that the project needs.<br>
**Project Subject Category Tree:** Category of the project.<br>
**Project Subject Subcategory Tree:** Subcategory of the project.<br>
**Project Grade Level Category:** Grade level that the project aims.<br>
**Project Resource Category:** Category of resources that the project needs.<br>
**Project Cost:** Costs of the project.<br>
**Project Posted Date:** Date when the project is posted.<br>
**Project Expiration Date:** Date when the project is expired.<br>
**Project Current Status:** Current status of the project.<br>
**Project Fully Funded Date:** Date when the project gets fullt funded.<br>

`resources.csv`

For every project in the Projects.csv file, there are one or more resources that is requested. This dataset contains the names of each resource in the project request and is joined with the dataset above using the “Project ID” column.

**Project ID:** Project ID<br>
**Resource Item Name:** The name of the requested item, as it appears on the vendor’s website.<br>
**Resource Quantity:** The quantity of the requested item.<br>
**Resource Unit Price:** The price per unit of the requested item.<br>
**Resource Vendor Name:** Name of the vendor.<br>

`schools.csv`

**School Name:** Name of the school.<br>
**School Metro Type:** One of four categories describing metro type, or urbanicity, of school area.<br>
**School Percentage Free Lunch:** Integer describing percentage of students qualifying for free or reduced lunch, obtained from NCES data. For schools without NCES data, a district average is used.<br>
**School State:** The state of the school that the teacher was teaching at at the time the project was posted.<br>
**School Zip:** The zip code of the school that the teacher was teaching at at the time the project was posted.<br>
**School City:** The city of the school that the teacher was teaching at at the time the project was posted.<br>
**School County:** The county of the school that the teacher was teaching at at the time the project was posted.<br>
**School District:** The district of the school that the teacher was teaching at at the time the project was posted.<br>

`teachers.csv`

**Teacher ID:** Unique identifier of a teacher.<br>
**Teacher Prefix:** “Mrs.”, “Ms.”, “Mr.”, “Teacher” (gender neutral option) chosen by teacher during account creation.<br>
**Teacher First Project Posted Date:** Date on which the teacher’s first project was posted.<br>