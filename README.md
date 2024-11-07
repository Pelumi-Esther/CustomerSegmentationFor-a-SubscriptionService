# CustomerSegmentationFor-a-SubscriptionService

### Objectives

 analyzing customer data for a subscription service to identify segments and trends. The data is explored so as to; 
 1. Understand customer behavior
 2. Track subscription types
 3. Identify key trends in cancellations and renewals

 ### Overview

The data analyzed for this report contains 3 distinct subscription type;
- Basic
- Standard
- Premium

Customers are spread across the following regions;
- South
- East
- North
- West

### About Data

The data analyzed was provided by The Incubator Hub [Download Here](https://docs.google.com/spreadsheets/d/1TmYiCGXgi4RYZtY07ek7CiI6ZzooFqpKhO0bA2ZrTpY/edit?usp=sharing). The dataset contains subscription purchase and status from the 4 different regions customers are located. The data originally contained 8 columns and 75001 rows, however, after cleaning the data we are left with 33788 rows and 13 columns.

| Column                  | Description                             | Data Type      |
| :---------------------- | :-------------------------------------- | :------------- |
| CustomerID              | Invoice of the purchase made            | VARCHAR(30)    |
| CustomerName            | Customer that made the purchase         | VARCHAR(30)    |
| Region                  | Region at which purchase was made       | VARCHAR(5)     |
| SubscriptionType        | Subscription type sold                  | VARCHAR(100)   |
| SubscriptionStart       | The date on which the purchase was made | DATE           |
| SSMonth                 | The month which the purchase was made   | VARCHAR(10)    |
| SSYear                  | The year which the purchase was made    | INT            |
| SubscriptionEnd         | The date on which the subscription ended| DATE           |
| SEMonth                 | The month which the subscription ended  | VARCHAR(10)    |
| SEYear                  | The year which the subcription ended    | INT            |
| SubscriptionDuration    | How long the subscription lasted        | INT            |
| Canceled                | Active and non-active subcription       | VARCHAR(5)     |
| Revenue                 | The amount paid by customer             | INT            |

### Tools Used 

- Google sheets for data cleaning, exploration and summarization.
- MS SQL Server for data querying.
- Tableau for data visualization.

### Key Questions

- Retrieve the total number of customers from each region.
- Find the most popular subscription type by the number of customers.
- Find customers who canceled their subscription within 6 months.
- Calculate the average subscription duration for all customers.
- Find customers with subscriptions longer than 12 months.
- Calculate total revenue by subscription type.
- Find the top 3 regions by subscription cancellations.
- Find the total number of active and canceled subscriptions.


### Data Cleaning and Preparation

- Identified and removed duplicates
- Checked for blank cells
- Ensured my data had clear headers
- Made the data consistent

### How New Columns were created

Subscription Start Month ............. ```  =TEXT(E2, "mmm") ```

Subscription Start Year ........... ``` =TEXT(E2, "yyy")) ```

Subscription End Month ............ ``` =TEXT(H2, "mmm") ```

Subscription End Year ............... ``` =TEXT(H2, "yyy")) ```

Subscription duration by month ....... ``` =DATEDIF(E2, H2, "M") ```


### Exploratory Data Analysis

The data was explored to provide answers to the following questions;

- Avg subscription duration

```  =AVERAGE(K2:K33788) ```

- Most popular subscription type

``` =COUNTIF(D2:D33788, "Basic") ```

``` =COUNTIF(D2:D33788, "Standard") ```

``` =COUNTIF(D2:D33788, "Premium") ```

### Data Analysis

``` Select * From CustomerSegmentation ```

See more [Here](https://github.com/Pelumi-Esther/CustomerSegmentationFor-a-SubscriptionService/blob/main/SQL_Queries)

### Data Visualization

![Dashboard 1 (1)](https://github.com/user-attachments/assets/8f7caa56-69fe-47ad-bdf8-c092bef02664)

### Insights

- **16,921** customers subscribed to the Basic plan, **8,446** to the Premium plan and **8,420** to the Standard plan.
- The Basic subscription type made the most revenue.
- The Basic subscription type is peculiar to the East and North, the Premium subscription type to the South, and the Standard subscription type to the West.
- **15,175** customers cancelled their subscription, while **18,612** customers have active subscription.

### Recommendation 

- Collecting of customer feedback should be prioritized, especially customers that cancelled their subscription.
- Improvements should be made based on the feedback collected from customers.
