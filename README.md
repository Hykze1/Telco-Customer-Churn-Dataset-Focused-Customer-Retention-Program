# Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program
USING EXCEL ONLY FOR DATA CLEANING, ANALYSIS AND VISUALIZATION

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/aa737df0-5bc8-4680-82a3-29ef50eb237e)

# Introduction
The dataset contains focused customer retention data of 7043 customers which includes CustomerID, Gender, SeniorCitizen, Partner, Dependents, Tenure, Phone Service, Multiple Lines, Internet Service, Online security, Online Backup, Device Protection, TechSupport, Streaming Tv, Streaming movies, Contract, Paperless billing, Payment Method, Monthly Charges, Churn. This data indicates customers that have left or stayed, currently using the services signed up for.

# Objectives
To predict insights from the Telco Customer Churn by which customers are retained or tend to leave based in each sectors in the dataset making the churn our target.

# Dataset Source

The dataset is a CSV file which contains a table entailing 7043 rows and 21 columns. The data was gotten from the data challenge group on telegram which was later downloaded from the Kaggle site https://www.kaggle.com/datasets/blastchar/telco-customer-churn

TOOL: Microsoft Excel 
https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/blob/main/Telco-Customer-Churnv1%20(Recovered).xlsx

# Exploratory Data Analysis (EDA)
EDA techniques are applied to gain insights into the dataset, identify patterns, and understand the distribution of variables.
# Checking for empty rows and blanks:
Selected all the dataset, then used =COUNTBLANK(A1:U7040). The dataset indicated that there was no blank rows and columns.

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/26b9b215-ec82-4dad-8531-509ec7b75336)

# Checking for duplicates
This is to check for the customerID column for any reoccurring and get rid of them because customerID must be unique in this case.
# Check and Convert columns to appropriate data types
noticed that most of the data set were in text format except the Tenure, Monthly Charges and Total charges. Since SENIOR CITIZEN Is more of yes/no question I changed the (0,1) to (No, Yes). 

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/75ff413b-4350-4977-8ee6-8c6c80085fd1)

# Grouping the Tenure column:
Noticed that the tenure represented the number of months each client has stayed with them which the highest was 72 months by using = MAX(F:F)
 
![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/1b38f65a-5a01-4e21-b261-e73343f8125c)

Let group the months from 1–12 months as “Short”, 12–24 months as “Intermediate” and 24 months and above as “Long” using conditional statement
 =IF(F2<=12, "Short", IF(F2<=24, "Intermediate", IF(F2<=72, "Long", "")))
![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/b368759c-d292-42a6-aa79-1c9b1968f485)

# Grouping the Contract column: 
By usung the formula =SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(TRIM([@Contract]), "Month-to-month", "Monthly"), "One year", "Annually"), "Two year", "biennially") we were able to do some replacement. Please take note of the trim because some of the cell in the column had extra space and this can be removed using trim

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/d0efa187-2953-43c3-9efb-f54a4fc5f99f)

# DESCRIPTIVE ANALYSIS
For a better understanding of the data distribution, we display summary statistics for numerical columns.
When attempting to do that (Alt+H+Y3) after highlighting the rang to describe we encountered an error 

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/6879f7ce-7b11-47f5-869e-af751d19add9)

Which means have a dataset with non-numeric data, hence it is either there are alphabet or special characters or blanks spaces in the cell because DESCRIBE only use numerical.
After much observation and troubleshooting it was observed that there were BLANKS spaces after all 
( Total Charges) and neither the formula COUNTBLANK(A1:U7040) or Ctrl + G + "Go To Special" dialog box, select "Blanks" and click "OK."  Are very effective. 
The most effective is either (Alt + H+L+N) + FORMAT ONLY THAT CONTAIN + BLANK or (Ctrl +H)
In the "Find what" field, enter a single space character by pressing the spacebar once and this will spill every blank spaces out. 

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/8b38301f-559c-4a65-9cd2-ba9d053fb023)

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/b2792958-3010-4707-814f-ddb0b48c9fa4)

# DATA REPRESENTATION
Insights on this dataset was performed using pivot table and Pivot charts for the dashboard in order to provide the answers to this dataset
POV: In this data interpretation “NO” means customer “Stayed” while “YES” means “Churn/Leave”

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/15fa59e0-d90b-4e3c-ba32-1e6fd01b805d)

Form the pivot table we can see that 1869/26.54% are Churned/left while 5174/ 73.46% customer are retained or stayed.

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/c3a77127-6434-4bf1-a60d-95db4f49223f)

In normal circumstance we are to investigate why it is blank and see how we can resolve it but for the purpose of this analysis
To resolve this issue, we decided to remove the 11 rows containing these empty values since they do not significantly impact the overall dataset.

# Distribution of Tenure for Churned and Stayed Customers'

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/de2da859-1808-4088-9689-01439a7d88f2)

It appears that new customers have a higher tendency to churn, and the likelihood of churn decreases over time as the customer's tenure with the company increases. This finding suggests that customer loyalty tends to strengthen over the course of their relationship with the telecommunications company. By understanding this trend, the company can focus on implementing targeted retention efforts for new customers to reduce churn and enhance customer satisfaction during the early stages of their service subscription.

# DISTRIBUTION OF GENDER AND CHURNED/STAYED CUSTOMERS'
Total number of customers churned:  we selected the churn and placed it into the field, make use of the count function for churn to get the total number of people that left which is 1869 customers and 5174 customers stayed;
Total number of both male and female customers: we selected the gender and placed it on the ROW field and churn at the VALUE field then get 3488 for female customers and 3555 for male customers, total number of female and male customers churned I selected both gender churn into the ROW field in the pivot table, we used the count function for the churn selected into the VALUE field; for the female we had total churn or customers that left to be 939 while female customers that stayed were 2549. While for the male we had total churn or customers that left to be 930 while female customers that stayed were 2676.

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/10685c33-8bc6-4bd3-9b69-4ebc62bfeb8a)

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/f585be15-4250-451c-a0f5-9c688a4b5e59)

# SERVICES USED BY CUSTOMERS
Let make all the services such as each customer has signed up for into pivot table and pivot chart which includes Phone services, customers who use multiple lines, who use internet service (fiber optic is an internet server, DSL is another internet server and No for those who did not use internet service), Online security, Online backup, Device protection, Streaming tv, Streaming movies and Tech support
POV: Yes- means customer signed up for that service, No-means customer did not sign up for that service and “No internet to service” means they do not have access to internet.

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/76adc166-041d-4fd3-8df2-86673a82c923)
![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/ad484f7b-495f-4b77-8bba-b2230e493a92)

# Let use just 4 services to get the number of people that left within the last month, since churn has value of “Yes” which equates the people that stopped using that service within the past month and “No” for people that still continued the service. I selected churn and kept it in the VALUE field
POV: “yes” means leave {churn} “no” means such customer stayed and ‘no internet service” means the customer did not have the internet connection to use that service.

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/9a647c4f-edb2-46a4-bfcb-7b19070ef520)

# CUSTOMER ACCOUNT INFORMATION
This was done to check some specifics of each customer which includes:
Contract: These includes customers who have stayed month-month 3875, stayed a year 1473 and customers who stayed two years is 1695
Paperless billing: These includes customers that used this type of bills “Yes” meaning they used paperless billing making 4171 customers and “No” meaning they did not use paperless billing making it 2872 customers
Payment method: Total customer who uses the best paying source through electronic check (2365), mailed check (1612), bank transfer (1544) and credit card (1522)
Tenure: This span for 0–12 months i.e., short (2186) then foe 12–24 months intermediate (1024) and finally from 24 months and beyond (3833)

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/a3e35af8-9ac2-4ba5-9e7f-5eacfeffa45d)

# DEMOGRAPHICS
This indicates more information about customers;
Gender: This dataset indicates the number of males (3555) and females (3488) that subscribed to the company services
Age Range: In terms of if they are Senior citizens (5901) or not senior citizens (1142)
Partners: If the customers are single (3402) or with partners (3641)
Dependents: Yes, meaning they are dependents (2110) and No if they are not dependents (4933)

![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/e4a1786c-376e-4693-a289-edc13fb1c0cd)

# DEMOGRAPHICS CHURN
This shows the number of customers that left the company within an age range, Gender, Partners, dependents.
# lastly we drop or delete unnecasary column like customerID since its not needed in our Analysis

# PROPOSITION DEDUCED FROM DATASET
# CUSTOMER’S ACCOUNT
1.	It was observed that there are trend where long-tenured staff are leaving at a higher rate than short-tenured staff, it's important to address this issue to maintain stability and ensure a positive work environment. Here are some pieces of advice:

1. **Conduct Exit Interviews**: Engage departing long-tenured employees in exit interviews to understand their reasons for leaving. This can provide valuable insights into any systemic issues or concerns that might be contributing to their departure.

2. **Review Compensation and Benefits**: Evaluate the compensation and benefits packages for long-tenured employees. If they feel undervalued in comparison to newer employees, it can be a major factor in their decision to leave.

3. **Career Development Opportunities**: Ensure that long-tenured employees have access to ongoing career development opportunities. This could include training, mentorship, promotions, or lateral moves within the company. Show them a clear path for growth and advancement.
4. **Recognition and Appreciation**: Recognize and celebrate the contributions of long-tenured employees. Regularly acknowledge their achievements and loyalty to the company. Feeling appreciated can go a long way in retaining valuable staff.
5. **Work-Life Balance**: Assess work-life balance and overall job satisfaction for long-tenured employees. Make sure they are not experiencing burnout or feeling overwhelmed. Consider flexible work arrangements or other initiatives that promote well-being.
6. **Feedback Mechanisms**: Establish regular feedback mechanisms for employees at all levels. Create a platform for long-tenured employees to voice their opinions, suggest improvements, and contribute to decision-making.
7. **Succession Planning**: Implement a robust succession planning process to ensure a smooth transition when long-tenured employees decide to leave. Identifying and grooming internal talent for key roles can help mitigate the impact of departures.

# 2.	It was noticed that the  company is experiencing a loss of customers due to issues with the electronic check transfer payment method, it's crucial to address this problem to prevent further customer attrition. Here are some pieces of advice to consider:

1. **Identify the Root Cause**: Begin by thoroughly analyzing the reasons for customer losses related to electronic check transfers. Is it a technical issue, a lack of convenience, security concerns, or something else? Understanding the root cause is essential for effective resolution.
2. **Improve User Experience**: Ensure that the electronic check transfer process is user-friendly and intuitive. Streamline the steps, eliminate unnecessary complexities, and provide clear instructions for customers to follow.
3. **Communication and Education**: Proactively communicate with customers about the benefits and security of electronic check transfers. Provide educational materials, tutorials, and FAQs to guide them through the process and alleviate any concerns they might have.
4. **Customer Support**: Ensure that customers have easy access to reliable customer support when using electronic check transfers. Promptly address any issues, questions, or concerns they may have, and offer multiple channels for assistance.
5. **Testing and Quality Assurance**: Regularly test and monitor the electronic check transfer system to identify and address any technical glitches, bugs, or errors that could be causing customer dissatisfaction.
6. **Incentives for Adoption**: Encourage customers to use electronic check transfers by offering incentives such as discounts, rewards, or cashback. This can motivate them to try the payment method and experience its benefits.

# 3.	It was also noticed that a significant loss of subscribers for a monthly subscription service, it's important to address this issue promptly to prevent further attrition and regain customer trust. Here are some pieces of advice to consider:

1. **Analyze Customer Feedback**: Gather feedback from the customers who have canceled their subscriptions. Understand the reasons behind their decisions. Conduct surveys, interviews, or online reviews to gain insights into their concerns and dissatisfaction.
2. **Improve Value Proposition**: Review and enhance the value proposition of your subscription service. Ensure that customers clearly understand the benefits they receive and how your service meets their needs or solves their problems.
3. **Enhance Content and Quality**: If your subscription service offers content (such as digital media, software, or educational resources), focus on consistently delivering high-quality and relevant content that justifies the subscription cost.
4. **Pricing and Plans**: Reevaluate your pricing strategy. Consider offering different subscription tiers or pricing plans to cater to a broader range of customers. Make sure the cost aligns with the perceived value of the service.
5. **Flexible Cancellation Policies**: Make it easy for customers to cancel their subscriptions if they choose to. A transparent and hassle-free cancellation process can help retain goodwill, even if customers decide to leave.
6. **Promotions and Incentives**: Offer limited-time promotions, discounts, or incentives to encourage new subscribers and win back those who have canceled. Highlight any improvements or changes you've made to address their previous concerns.
7. **Customer Support and Assistance**: Provide excellent customer support that is readily available to address any issues or concerns. Promptly respond to inquiries and resolve problems to showcase your commitment to customer satisfaction.
8. **User Experience and Interface**: Ensure that the user interface and overall user experience of your subscription service are intuitive, user-friendly, and easy to navigate. A positive user experience can encourage subscribers to stay.

# SERVICES
# 1.	We observe that the company is losing customers through its fiber optic internet service, it's important to address this issue promptly to retain existing customers and attract new ones. Here are some pieces of advice to consider:

1. **Service Quality and Reliability**: Ensure that your fiber optic internet service is consistently delivering high-quality, reliable, and high-speed connectivity. Invest in infrastructure, maintenance, and monitoring to minimize downtime and service disruptions.
2. **Customer Support and Communication**: Offer excellent customer support that is readily available to address technical issues, answer questions, and provide assistance. Communicate proactively with customers about any planned maintenance or disruptions and provide clear timelines for resolution.
3. **Pricing and Value Proposition**: Evaluate your pricing strategy to ensure that it aligns with the perceived value of the service. Demonstrate how your fiber optic service offers a competitive advantage in terms of speed, stability, and overall performance.
4. **Competitor Analysis**: Research and understand the offerings of competitors in the fiber optic internet market. Identify your unique selling points and differentiate your service through innovative features, bundle offerings, or superior customer experience.
5. **Feedback Collection**: Gather feedback from customers who have switched to other providers. Understand their reasons for leaving and use this information to address specific pain points or shortcomings in your service.
6. **Promotions and Incentives**: Offer promotions, discounts, or incentives to attract new customers and win back those who have left. Highlight any improvements or enhancements you've made to address previous concerns.
7. **Performance Transparency**: Provide customers with transparent information about the actual performance and speed of your fiber optic service. Offer tools for customers to monitor their own connection quality and speed.
8. **Partnerships and Alliances**: Form partnerships with relevant technology companies, content providers, or entertainment platforms to enhance the value of your fiber optic service. Bundling services can make your offering more appealing.
9. **Long-Term Contracts and Loyalty Programs**: Consider offering long-term contract options or loyalty programs that provide incentives for customers to stay with your fiber optic service over time.
10. **Employee Training**: Ensure that your customer-facing employees are well-trained and equipped to provide accurate information and support. Their knowledge and professionalism can greatly impact customer satisfaction.

# THE DASHBOARD
![image](https://github.com/Hykze1/Telco-Customer-Churn-Dataset-Focused-Customer-Retention-Program/assets/100960483/2ae82ccb-4d3e-4edc-8590-5e146cbcfa16)





