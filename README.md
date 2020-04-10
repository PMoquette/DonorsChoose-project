![Ironhack logo](https://i.imgur.com/1QgrNNw.png)

# DonorsChoose | Data Analysis Project

## Project Description:

Final Ironhack project.<br>
The purpose of this project is to gain insights into donor behavior and project preferences based on the data provided by [DonorsChoose.org](https://www.donorschoose.org/) 

DonorsChoose.org partnered with Google.org and shared this [Data](https://www.kaggle.com/donorschoose/io) on Kaggle for as an invitation to help them "pair up donors to the classroom requests that will most motivate them to make an additional gift. To support this challenge, DonorsChoose.org has supplied anonymized data on donor giving from the past five years. The winning methods will be implemented in DonorsChoose.org email marketing campaigns."

### Codebook:

`donations.csv`

For every project in the Projects.csv dataset, there are one or more donations. This dataset contains each donation from a citizen donor and is joined with the dataset above using the “Project ID” column.testt test1

**Project ID** Unique ID of a project
**Donation ID** Unique ID of a donation
**Donor ID** Unique ID of a donor
**Donation Included Optional** DonationYes/No to give 15% of donation amount to Donoschoose
**Donation Amount** Total amount donated for a project
**Donor Cart Sequence** Project position on list of desired donations within Cart list.
**Donation Received Date** Date and time on which the donation was recieved

`donors.csv`

For every project in the Projects.csv dataset, there are one or more donations. This dataset contains each donation from a citizen donor and is joined with the dataset above using the “Project ID” column.testt test1

**Donor ID** Unique identifier of a donor.
**Donor City** The donor’s city.
**Donor State** The donor’s state.
**Donor Is Teacher** Whether or not the donor is also a teacher with a DonorsChoose.org teacher account.
**Donor Zip** The donor’s zip code (only first 3 digits).

`projects.csv`

For every project in the Projects.csv dataset, there are one or more donations. This dataset contains each donation from a citizen donor and is joined with the dataset above using the “Project ID” column.testt test1

**Project ID:** Unique identifier of a project.
**School ID:** Unique identifier of a school where the project is proposed from.
**Teacher ID:** Unique identifier of a teacher who proposed the project.
**Teacher Project Posted Sequence:** Represents the order as a project issued by the teacher.
**Project Type:** Type of the project.
**Project Title:** Title of the project.
**Project Essay:** Essay of the project.
**Project Short Description:** Description of the project.
**Project Need Statement:** Statement for the resources that the project needs.
**Project Subject Category Tree:** Category of the project.
**Project Subject Subcategory Tree:** Subcategory of the project.
**Project Grade Level Category:** Grade level that the project aims.
**Project Resource Category:** Category of resources that the project needs.
**Project Cost:** Costs of the project.
**Project Posted Date:** Date when the project is posted.
**Project Expiration Date:** Date when the project is expired.
**Project Current Status:** Current status of the project.
**Project Fully Funded Date:** Date when the project gets fullt funded.

`resources.csv`

For every project in the Projects.csv file, there are one or more resources that is requested. This dataset contains the names of each resource in the project request and is joined with the dataset above using the “Project ID” column.

**Project ID:** Project ID
**Resource Item Name:** The name of the requested item, as it appears on the vendor’s website.
**Resource Quantity:** The quantity of the requested item.
**Resource Unit Price:** The price per unit of the requested item.
**Resource Vendor Name:** Name of the vendor.