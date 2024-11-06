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

![Screenshot 2024-11-06 155807](https://github.com/user-attachments/assets/12ffc6d1-5e80-4360-a52a-26ca32c13319)

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

![Screenshot 2024-11-06 171332](https://github.com/user-attachments/assets/be9ca7b4-f756-455b-be60-ef088963ee62)

### 2.  Find the most popular subscription type by the number of customers.

![Screenshot 2024-11-06 171529](https://github.com/user-attachments/assets/74d4501c-4490-4808-b561-c15480f73867)

### 3.  Find customers who canceled their subscription within 6 months.
![Screenshot 2024-11-06 171754](https://github.com/user-attachments/assets/5e44667e-5dc0-4e4c-968e-5f44263c0ac4)

### 4.  calculate the average subscription duration for all customers. 

