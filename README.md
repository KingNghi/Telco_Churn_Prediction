# **Project Background**

Telco is a telecommunications company that offers various services, including phone and internet services. This sample data tracks the company's customer churn based on a variety of possible factors. The churn column indicates whether or not the customer left within the last month. Other columns include gender, dependents, monthly charges, and many with information about the types of services each customer has. This project conducts a comprehensive analysis of the dataset to identify the factors influencing customer churn. Additionally, we aim to develop a machine learning model that empowers stakeholders to predict potential churn among customers effectively.

Insights and recommendations are provided on the following key areas:

- **Service:** The way Telco interact with customers, which influences their behavior or decision to churn out.
- **Product:** The actual value customers get from Telco.

Full Python code can be accessed via this: https://github.com/KingNghi/Telco_Churn_Prediction/blob/main/Telco_Churn_Prediction.ipynb

# **Data Structure & Initial Checks**

The Telco customer churn data module is composed of 3 uploaded files:

- Telco_customer_churn_demographics.xlsx
- Telco_customer_churn_services.xlsx
- Telco_customer_churn_status.xlsx

 A description of each table is as follows:

- **Demographics**
    - CustomerID: A unique ID that identifies each customer.
    - Count: A value used in reporting/dashboarding to sum up the number of customers in a filtered set.
    - Gender: The customer’s gender: Male, Female
    - Age: The customer’s current age, in years, at the time the fiscal quarter ended.
    - Senior Citizen: Indicates if the customer is 65 or older: Yes, No
    - Married: Indicates if the customer is married: Yes, No
    - Dependents: Indicates if the customer lives with any dependents: Yes, No. Dependents could be children, parents, grandparents, etc.
    - Number of Dependents: Indicates the number of dependents that live with the customer.
- **Services**
    - CustomerID: A unique ID that identifies each customer.
    - Count: A value used in reporting/dashboarding to sum up the number of customers in a filtered set.
    - Quarter: The fiscal quarter that the data has been derived from (e.g. Q3).
    - Referred a Friend: Indicates if the customer has ever referred a friend or family member to this company: Yes, No
    - Number of Referrals: Indicates the number of referrals to date that the customer has made.
    - Tenure in Months: Indicates the total amount of months that the customer has been with the company by the end of the quarter specified above.
    - Offer: Identifies the last marketing offer that the customer accepted, if applicable. Values include None, Offer A, Offer B, Offer C, Offer D, and Offer E.
    - Phone Service: Indicates if the customer subscribes to home phone service with the company: Yes, No
    - Avg Monthly Long Distance Charges: Indicates the customer’s average long distance charges, calculated to the end of the quarter specified above.
    - Multiple Lines: Indicates if the customer subscribes to multiple telephone lines with the company: Yes, No
    - Internet Service: Indicates if the customer subscribes to Internet service with the company: No, DSL, Fiber Optic, Cable.
    - Avg Monthly GB Download: Indicates the customer’s average download volume in gigabytes, calculated to the end of the quarter specified above.
    - Online Security: Indicates if the customer subscribes to an additional online security service provided by the company: Yes, No
    - Online Backup: Indicates if the customer subscribes to an additional online backup service provided by the company: Yes, No
    - Device Protection Plan: Indicates if the customer subscribes to an additional device protection plan for their Internet equipment provided by the company: Yes, No
    - Premium Tech Support: Indicates if the customer subscribes to an additional technical support plan from the company with reduced wait times: Yes, No
    - Streaming TV: Indicates if the customer uses their Internet service to stream television programing from a third party provider: Yes, No. The company does not charge an additional fee for this service.
    - Streaming Movies: Indicates if the customer uses their Internet service to stream movies from a third party provider: Yes, No. The company does not charge an additional fee for this service.
    - Streaming Music: Indicates if the customer uses their Internet service to stream music from a third party provider: Yes, No. The company does not charge an additional fee for this service.
    - Unlimited Data: Indicates if the customer has paid an additional monthly fee to have unlimited data downloads/uploads: Yes, No
    - Contract: Indicates the customer’s current contract type: Month-to-Month, One Year, Two Year.
    - Paperless Billing: Indicates if the customer has chosen paperless billing: Yes, No
    - Payment Method: Indicates how the customer pays their bill: Bank Withdrawal, Credit Card, Mailed Check
    - Monthly Charge: Indicates the customer’s current total monthly charge for all their services from the company.
    - Total Charges: Indicates the customer’s total charges, calculated to the end of the quarter specified above.
    - Total Refunds: Indicates the customer’s total refunds, calculated to the end of the quarter specified above.
    - Total Extra Data Charges: Indicates the customer’s total charges for extra data downloads above those specified in their plan, by the end of the quarter specified above.
    - Total Long Distance Charges: Indicates the customer’s total charges for long distance above those specified in their plan, by the end of the quarter specified above.
- **Status**
    - CustomerID: A unique ID that identifies each customer.
    - Count: A value used in reporting/dashboarding to sum up the number of customers in a filtered set.
    - Quarter: The fiscal quarter that the data has been derived from (e.g. Q3).
    - Satisfaction Score: A customer’s overall satisfaction rating of the company from 1 (Very Unsatisfied) to 5 (Very Satisfied).
    - Satisfaction Score Label: Indicates the text version of the score (1-5) as a text string.
    - Customer Status: Indicates the status of the customer at the end of the quarter: Churned, Stayed, or Joined
    - Churn Label: Yes = the customer left the company this quarter. No = the customer remained with the company. Directly related to Churn Value.
    - Churn Value: 1 = the customer left the company this quarter. 0 = the customer remained with the company. Directly related to Churn Label.
    - Churn Score: A value from 0-100 that is calculated using the predictive tool IBM SPSS Modeler. The model incorporates multiple factors known to cause churn. The higher the score, the more likely the customer will churn.
    - Churn Score Category: A calculation that assigns a Churn Score to one of the following categories: 0-10, 11-20, 21-30, 31-40, 41-50, 51-60, 61-70, 71-80, 81-90, and 91-100
    - CLTV: Customer Lifetime Value. A predicted CLTV is calculated using corporate formulas and existing data. The higher the value, the more valuable the customer. High value customers should be monitored for churn.
    - CLTV Category: A calculation that assigns a CLTV value to one of the following categories: 2000-2500, 2501-3000, 3001-3500, 3501-4000, 4001-4500, 4501-5000, 5001-5500, 5501-6000, 6001-6500, and 6501-7000.
    - Churn Category: A high-level category for the customer’s reason for churning: Attitude, Competitor, Dissatisfaction, Other, Price. When they leave the company, all customers are asked about their reasons for leaving. Directly related to Churn Reason.
    - Churn Reason: A customer’s specific reason for leaving the company. Directly related to Churn Category
# Executive Summary

### Overview of Findings

The 2 main reasons of Telco boil down to the service behavior and the product quality of Telco.  The three main insights to take away from this project focus on customer engagement and retention strategies. First, short-term contracts can lead to a lack of commitment, as customers often prefer to sample services before committing long-term, highlighting the need for an improved onboarding process and service quality during this trial phase. Second, the attitude and training of personnel significantly influence customer satisfaction and retention; enhancing customer support could lower churn rates. Lastly, the current product offerings, particularly in internet quality, need to be assessed and upgraded to meet customer expectations better, thus increasing the likelihood of customer adoption and loyalty.

[Visualization, including a graph of overall trends or snapshot of a dashboard]



# Insights Deep Dive
### Service:

- Contract:  Customers feel less committed on short-term contract such as month-to-month contract. This could be due to the fact that customers want to sample a service first before investing in it in the long term. And during the trial, a number of customers are dissatisfied with the quality of both product and service of Telco.
  
- Attitude: The attitude of personels from Telco contributes to a large amount of churn decision of customers, making the most satisfaction score is 3.

[Visualization specific to category 1]


### Product:

The available options are not quality enough to attract customers, leading to the fact that not many customers choose any offers.
  
Even if they do choose offers, some of those offers don’t live up to their expectation, such as option E. One of the main reasons could derive from the poor quality of internet type, specifically Fiber Optic. 

[Visualization specific to category 2]

# Recommendations:

Based on the insights and findings above, we would give these recommendations: 

- Enhance Customer Onboarding and Trial Experience: Develop a comprehensive onboarding program for new customers on month-to-month contracts that emphasizes quality service experiences. This may include personalized account setup assistance and regular follow-ups during the trial period to address any issues promptly, ensuring that customers feel supported and valued.
- Invest in Staff Training and Development: Implement ongoing training programs focused on customer service excellence for personnel at Telco. This training should prioritize effective communication, empathy, and problem-resolution skills to improve overall customer interactions and satisfaction scores.
- Upgrade Product Offerings: Conduct a thorough review and upgrade of current service offerings, particularly focusing on the quality of internet services (e.g., Fiber Optic). Introduce competitive packages that meet market expectations and clearly communicate the benefits of these offerings to potential customers, ensuring that they align with customer needs.
- Implement Customer Feedback Mechanisms: Establish regular customer feedback channels, such as surveys and focus groups, to gather insights on customer satisfaction and expectations. Use this feedback to iteratively improve service quality and product offerings, demonstrating Telco's commitment to meeting customer needs.
- Create Attractive Long-Term Incentives: To encourage transition from month-to-month to longer commitments, consider implementing loyalty programs or exclusive benefits for customers who opt for one- or two-year contracts. These could include discounts, enhanced service features, or bonuses for referrals, thus fostering a sense of community and commitment to Telco.
  


