# LITA-CAPSTONE-PROJECT-2

## CUSTOMER SEGMENTATION FOR A SUBSCRIPTION SERVICE 

## Dataset
![Screenshot 2024-11-06 141047](https://github.com/user-attachments/assets/7f7eb862-4986-4de3-8fef-66ed8bb8caf0)

## Project Overview
This project involves analyzing customer data for a subscription service to identify segments and trends; understand customer behavior, track subscription types, and identify key trends in cancellations and renewals

## Data Description
The dataset  includes the following key columns:
1. Customer ID: A unique identifier associated with each suscriber
2. Customer name: The name of each subscriber.
4. Region: The geographic location of the Subscription.
5. Subscription type: Type of subscription (Basic, Standard, Premium) 
6. SubscriptionStart: Start date of the subscription
7. SubscriptionEnd: End date of the subscription
8. Canceled: Whether or not the subscription was canceled (TRUE/FALSE)
9. Revenue: Revenue generated from the subscription

## Data Source
This dataset that was freely provided by the facilitator. 

## Time Period
The dataset spans from 2022-2024

## Explorative Data Analysis
This project was designed to derive the following insights:

- Key customer segments
- Subscription cancellations
- Subscription trends.

 ## Tools and Methods Used

**Data cleaning** : Removal of duplicates; This was done using the "conditional formatting and "remove duplicate" function of Microsoft excel. Power query was further utilized to ensure column quality and data consistency.

**Data Analysis**: The data was analyzed using Microsoft Excel, utilizing Pivot Tables to organize, summarize, and filter the data for easier interpretation.
               SQL was utilized to query the data for further insights.
               
**Data Visualization**: Utilizing Power BI, Different visualizations were created represent the key insights.

## ANALYSIS, VISUALIZATION, AND INFERENCE

## Excel  Analysis
### 1. Average subscription duration

![Screenshot 2024-11-06 151528](https://github.com/user-attachments/assets/a9a142f6-7fc1-4052-8b14-50370225b0b1)
![Screenshot 2024-11-06 161931](https://github.com/user-attachments/assets/0d8b7542-83ef-4d97-a907-13b2a44bc0e3)

### 2. Most popular subscription types.

![Screenshot 2024-11-07 083223](https://github.com/user-attachments/assets/133e4642-4301-40ce-bd67-3124a6c4277a)


### 3. Cancellation rate per Subscription

![Screenshot 2024-11-06 160845](https://github.com/user-attachments/assets/428e7b6f-f7e4-47c7-b5c0-771ca8dec772)

### 4. Cancellation rate per Region

![Screenshot 2024-11-06 161440](https://github.com/user-attachments/assets/9c1d65bc-603a-44f3-b376-0eb16a6d1274)

### 5. Monthly subscription trend

![Screenshot 2024-11-06 155105](https://github.com/user-attachments/assets/5529d1f8-5d65-463e-aae8-f9ab3cbb5784)

### 6. Subscription Count by region

![Screenshot 2024-11-06 155930](https://github.com/user-attachments/assets/ddccde8e-25f6-4d1a-8213-5d500ec0c9d3)

### 7. Total revenue per region

![Screenshot 2024-11-06 160401](https://github.com/user-attachments/assets/22446024-af78-445b-b40e-b71cb094bdf7)

## Using SQL queries to extract key insights 

### 1.  Retrieve the total number of customers from each region. 
```
SELECT Region, COUNT(CustomerID)
AS Total_no_of_customers
FROM dbo.customerdata
GROUP BY Region
```

![Screenshot 2024-11-06 171332](https://github.com/user-attachments/assets/be9ca7b4-f756-455b-be60-ef088963ee62)

### 2.  Find the most popular subscription type by the number of customers.
```
SELECT TOP 1 Subscriptiontype,COUNT(CustomerID)
AS No_of_Customers
FROM dbo.customerdata
GROUP BY Subscriptiontype
```

![Screenshot 2024-11-07 082913](https://github.com/user-attachments/assets/623fb41b-5eb4-4159-8869-4b522ce4445e)

### 3.  Find customers who canceled their subscription within 6 months. Al subscription were for 12 months and higher, so none
```
SELECT CustomerID, SubscriptionType, Region, 
       DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) AS Subscription_Duration
FROM customerdata
WHERE DATEDIFF(MONTH, SubscriptionStart, SubscriptionEnd) <= 6
  AND Canceled = 'TRUE';
```

![Screenshot 2024-11-07 083638](https://github.com/user-attachments/assets/c79de82f-23c7-4e59-ac38-4ada59bd25ef)

### 4.  calculate the average subscription duration for all customers. 
```
SELECT Count(CustomerID) 
As All_Customers,AVG(DATEDIFF(DAY,SubscriptionStart,SubscriptionEND))
AS Average_Subscription_Duration
FROM dbo.customerdata
WHERE SubscriptionEnd IS NOT NULL
```

![Screenshot 2024-11-06 204836](https://github.com/user-attachments/assets/2c54f06c-6341-449d-b3c8-03afac81dac0)

### 5.  Find customers with subscriptions longer than 12 months.
```
SELECT CustomerName,SubscriptionType,SubscriptionStart,SubscriptionEnd
FROM dbo.customerdata
WHERE DATEDIFF(MONTH,SubscriptionStart,SubscriptionEnd) >12
```
![Screenshot 2024-11-07 084515](https://github.com/user-attachments/assets/c740cd23-b078-4115-981d-a54f0f17913f)

### 6.  Calculate total revenue by subscription type.
```
SELECT SubscriptionType,SUM(Revenue) AS Total_Revenue
FROM Customerdata
GROUP BY SubscriptionType
```
![Screenshot 2024-11-06 205255](https://github.com/user-attachments/assets/5882092c-04ba-4dd0-9b86-8a6551de6da6)

### 7.  Find the top 3 regions by subscription cancellations. 
```
SELECT TOP 3 region, COUNT(CustomerID) AS Total_Cancellations
FROM Customerdata
WHERE Canceled = 'TRUE'
GROUP BY Region
ORDER BY Total_Cancellations DESC;
```
![Screenshot 2024-11-07 085006](https://github.com/user-attachments/assets/d3f7814e-34e0-4694-8fe9-f054ef750955)

### 8.  Find the total number of active and canceled subscriptions.
```
SELECT Canceled, COUNT(CustomerID) AS Total_Subscriptions
FROM Customerdata
GROUP BY Canceled;
```
![Screenshot 2024-11-07 085317](https://github.com/user-attachments/assets/a753cd31-0f67-4b7a-8b90-871156947404)



