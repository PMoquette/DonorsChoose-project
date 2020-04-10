![Ironhack logo](https://i.imgur.com/1QgrNNw.png)

# DonorsChoose | Data Analysis Project

## Project Description:

Final Ironhack project.

The purpose of this project is to gain insights into donor behavior and project preferences based on the data provided by [DonorsChoose.org](https://www.donorschoose.org/) 

DonorsChoose.org partnered with Google.org and shared this [Data](https://www.kaggle.com/donorschoose/io) on Kaggle as an invitation to help them "pair up donors to the classroom requests that will most motivate them to make an additional gift. To support this challenge, DonorsChoose.org has supplied anonymized data on donor giving from the past five years. The winning methods will be implemented in DonorsChoose.org email marketing campaigns."

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