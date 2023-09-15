# YouFood, WeFood, iFood

<img src="images/iFood Post Pic.jpg?raw=true">

This project was the first of many in the Data Analytics Bootcamp led by Avery Smith. This first project helped me explore Excel and understand important functions and tools used daily in analytics. This first module in the bootcamp also introduced me to writing projects and posting them to share my findings. <br>

iFood is a company similar to DoorDash that operates in Brazil and Columbia. The dataset used for this project included sales and demographic information for the years of 2014 to 2016.<br><br>

### With the help of Excel, here's what I learned:
<ol>
  1. $1.24 million was spent on iFood from 2014 to 2016<br>
  2. 67% of the spend variance can be explained by income levels<br>
  3. New Memberships to iFood averaged 183 per month across all age ranges with more activity January, March, July & September, while the      months with the least amount of new memberships were October, November & December.<br>
  4. The age range that spends the most is customers between 36 & 65 years old
</ol>

### Let's Start with the Data!
Link to Data (from 2014-2016)
[iFood Data Set](https://www.kaggle.com/datasets/jackdaoud/marketing-data)

<br><br>

### Spending Based on Your Salary
I took the Income and Amount Spent by the customers in the dataset and created this scatter plot:<br><br>
<img src="images/Income vs Total Spent.png?raw=true"><br>

I was able to fit a line to this relationship that had an R-squared value of .67 meaning that we can predict, with almost 70% accuracy, how much a customer will spend on iFood Deliveries next year solely based on their income. There are two outliers which present the opposite: the first case presents with high income but spent significantly less than the majority and the other spent significantly more while having a lower income. The first scenario could have been a customer who participated in a promotion where a family member sent them a coupon and they utilized it on one occasion but don't typically utilize iFood in their everyday lives. In the second case, this could be a customer who is having difficulty with managing their money and is spending way too much on food delivery service than their budget would allow.<br><br>

### More Deliveries Every Month
Here we see the total number of new memberships monthly:<br><br>
<img src="images/Joins by Age Group.png?raw=true"><br>

In the age groups of 36-50 and 51-65, there is a steady increase in the number of new memberships as we move through the year.
<br><br>

These age groups also spend the most money on iFood collectively:<br><br>
<img src="images/Total Spent by Age Group.png?raw=true"><br>

Although we can see the age groups of 24-35 and 66+ grow steadily throughout the year, it's clear that the majority of revenue comes from the other two groups. This can help inform decisions on timing of campaigns and marketing strategies. New memberships in these age groups peak around October, November and December which are holiday-heavy months; appealing to family gatherings and ordering in instead of leaving the comfort of your home could prove to be most effective during this time of year.<br><br>

### Key Insights
Analyzing this data can help inform business decisions that can help grow iFood even more. Focusing on the age ranges (36 to 65) in relation to the time of year and the annual income of the customer you can leverage campaigns to maximize profitability.
