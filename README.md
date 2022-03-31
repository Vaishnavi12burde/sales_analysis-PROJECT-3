# A Data Analysis Project


## Sales data analysis in Power Bi


### PART I — Problem Statement

AtliQ hardware is a company in India which supplies computer hardware and peripheral devices across India only. The have many stores across India such as surge stores, Nomad stores etc. The head office of the company is situated in Delhi.
Scenario —

The sales manager of the company is facing many challenges. He is facing issues in tracking sales in dynamically growing market. He is having issues with the insights of his business.
In order to this he has some of the regional managers in North, south and central India working for the company. So, he calls them and ask about the insights he wants to know. They tell him about the sales in last quarter and the growth in that quarter.

So, the problem is that the conversations that are happening are verbal. Hence, the regional managers are sugar coating the facts and the manager of the company does not get the clear picture of the facts. Even after knowing that the sales are declining, he cannot do anything because he does not have the clear picture of the sales. Asking for the records the regional manager provides him with excel files. But by this he cannot figure out small things.

All what the manager wants is a view of the weakest area the company need to focus to increase the sales and improvise the declination. He is interested in simple, understandable and digestive insight. So, he is more interested in a dashboard which he can go and look at the real data because data speaks the truth. All he wants is a simple data visualization tool which he can access on daily basis.
Hence, by using such tools and technology one can make data driven decisions which helps to increase the sales of the company.
So, in this project we will help a company make its own sales related dashboard using PowerBI.


### PART II — Data Discovery

Project planning using AIMS grid –
AIMS grid: It is a project management tool which consists of four components to it.
1) Purpose (what to do exactly)
2) Stack holders (who will be involved)
3) End result (what do you want to achieve)
4) Success criteria (cost optimization and time save)
In our case the end result will be the dashboard created and success criteria will be bumping up the sales using cost optimization and save the time of the manager of the company.![1](https://user-images.githubusercontent.com/101336439/161124589-ecde8336-06d9-4691-9579-f0cca9c674e4.png)


Flowchart of the project execution –

How will the company work —
There is a team of software engineers (falcons) which owns sales management system. The records of this system are stored in MySQL database.
The team of Data Analyst (Data masters) reaches out to the software engineers to get an access to data base which they can use to create the dashboard in PowerBI.
In this same manner our project is going to be executed. We are going to fetch the data from the database from company’s website and then we are going to transform and load the data in the PowerBI to build the dashboard.

### PART III — Data Analysis using SQL

## Step 1: Importing Data to MySQL workbench

The import of data is done from an already existing MySQL file. This file has to be loaded into MySQL workbench for further data analysis.
The following images show that the import is a success.


## Step 2: Simple analysis of data by looking into different tables and reflecting garbage values

Here, we can see that the table market contains certain values which are incorrect. AtliQ hardware company works only in India but there are some records of different non-existing cities in India.

Here, we can see that table transactions contain certain negative value in amount which is not possible.

Here, you can see that certain transactions are in USD. Hence, filtration of that is also needed by converting into INR.




## Step 3: Primary analysis of data base by running different SQL statements

1. To find out how many total records are there in transaction table.

2. To find number of records in customer table.

3. Show transactions for Chennai market (market code for chennai is Mark001

4. Show distrinct product codes that were sold in chennai.
    `
5. Show transactions where currency is US dollars
 
6. Show transactions in 2020 join by date table

7. Show total revenue in year 2020,

8. Show total revenue in year 2020, January Month,

9. Show total revenue in year 2020 in Chennai

    

Data Analysis Using Power BI
============================

1. Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`



![Screenshot (280)](https://user-images.githubusercontent.com/101336439/161137914-8438925e-6249-43df-b78d-2f67a6eb34c2.png)
![Screenshot (281)](https://user-images.githubusercontent.com/101336439/161137926-550fbf79-0090-4130-a17f-97dc1c2375c2.png)
![Screenshot (282)](https://user-images.githubusercontent.com/101336439/161137933-8d80edd8-b3f5-49df-a60d-ba234887cb9e.png)



