# Telco Customer Churn

## About

[Dataset pulled from Kaggle.](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
Fictional telecom company, Telco, has data about their customers. Each row represents a customer, each column contains customer’s attributes described on the column Metadata.

The data set includes information about:

* Customers who left within the last month – the column is called Churn
* Services that each customer has signed up for – phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies
* Customer account information – how long they’ve been a customer, contract, payment method, paperless billing, monthly charges, and total charges
* Demographic info about customers – gender, age range, and if they have partners and dependents

## Goal

Develop customer retention programs by analyzing the relationship between customer characteristics and their churn rate

## Data cleaning Steps

* Finding null values in numeric columns
If a column that represents numeric values (e.g. Monthly Charges) contains null values, it needs to be investigated
Total Charges column has 11 rows that are missing values which also had a tenure value of 0. These contradictory rows were filtered for and deleted.

![Image](screenshots/2023-05/EXCEL_NIoNdMJWEa.png)

* Changed Senior Citizens values from (0,1) to  

![Image](screenshots/2023-05/EXCEL_ndb9UdweL5.png)

(Yes, no) Using IF statement  

![Image](screenshots/2023-05/EXCEL_fFT9besdbI.png)

* Added a "Number of Services" column that counts how many services the customer is subscribed to

![Image](screenshots/2023-05/EXCEL_axjuF7tTMM.png)

Using a COUNTIF() statement to count how many cells don't contain "No"

``` 
=COUNTIF(H2:O2, "<>*No*")
```

Our data is sufficiently cleaned and ready for analysis


## Exploratory Data Analysis

We'll begin by making pivot tables to help visualize relationships between churn and other independent variables.

Let's begin our investigation with Number of Services. 
![Image](screenshots/2023-06/EXCEL_08xEyMygVe.png)
With an R<sup>2</sup> value of 0.6259, we can say there's a moderately strong positive relationship. 
Customers that have more concurrent services are less likely to cancel their services. We can make the reccomendation to Telco to incentivize subscribing to more services by offering bundle discounts.


Next we'll investigate if senior citizens are churning at a higher rate

![Image](screenshots/2023-06/EXCEL_ozFMMSoCg3.png)

We can see that the proportion of seniors churned is double that of non-seniors. A reccomendation we can make to Telco is to offer senoir citizen discounts

As a final example, lets investigate Contract length

![Image](screenshots/2023-06/EXCEL_ZzbL81YeRy.png)

We can see that of the customers that churned, the overwhelming majority had a month-to-month contract. We can make a reccomendation to Telco to offer better discounts for signing up for yearly contracts



