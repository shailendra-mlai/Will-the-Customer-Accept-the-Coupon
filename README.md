# Will-the-Customer-Accept-the-Coupon
Professional Certificate in Machine Learning and Artificial Intelligence. Practical Application Assignment 5.1: Will the Customer Accept the Coupon?

**Context**

Imagine driving through town and a coupon is delivered to your cell phone for a restaraunt near where you are driving. Would you accept that coupon and take a short detour to the restaraunt? Would you accept the coupon but use it on a sunbsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaraunt? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?

Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

**Overview**

The goal of this project is to use what you know about visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those that did not.

**Data**

This data comes from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. Answers that the user will drive there ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’. There are five different types of coupons -- less expensive restaurants (under $20), coffee houses, carry out & take away, bar, and more expensive restaurants ($20 - $50).

**The Jupyter Notebook covers the following:**

1. Read in the coupons.csv file.
2. Investigate the dataset for missing or problematic data:
   * using data.columns , data.info().
   * Look for null value using data.isna().sum())
   * Car column has 99% null Values
3. Decide what to do about your missing data
   * Car column has 99% null Values. Dropping the car column.
   * Below are the missing Values which are around 1% rows. Dropping those row with NaN
   * Bar 107 CoffeeHouse 217 CarryAway 151 RestaurantLessThan20 130 Restaurant20To50 189
4. What proportion of the total observations chose to accept the coupon?
   * The number of users that are accepted the coupon is  6877 , 56.934 %
   * The number of users that are rejected the coupon is  5202 , 43.066 %
5. Used Seaborn bar plot to visualize the coupon column
6. Used Plotly histogram to visualize the temperature column.

**Investigating the Bar Coupons**

1. Create a new DataFrame that contains just the bar coupons.
2. What proportion of bar coupons were accepted?
   * Ratio of Bar Coupons accepted and Bar Coupons offered 0.41191845269210664 or 41.192 %
   * Ratio of Bar Coupons accepted and Coupons accepted 0.11458484804420532 or 11.458%
   * Ratio of Bar Coupons accepted and Coupons Offered 0.06523718850898254 or 6.524%
3. Compare the acceptance rate between those who went to a bar 3 or fewer times a month to those who went more.
   * Acceptance rate of driver those who went to bar 3 or less times a month is 81.345%
   * Acceptance rate of driver those who went to bar 3 or more times a month is 18.655 %
4. Compare the acceptance rate between drivers who go to a bar more than once a month and are over the age of 25 to the all others. Is there a difference?
   * Acceptance for drivers who go to a bar more than once a month and are over the age of 25 is 35.279%
   * Acceptance for drivers who go to a bar less than once a month and are under the age of 25 is 15.228 %
5. The acceptance rate of drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry is 17.132%
6. Compare the acceptance rates between those drivers who:
   * Acceptance rate of drivers who go to bars more than once a month, had passengers that were not a kid, and were not widowed is 17.132%
   * Acceptance rate of drivers who go to bars more than once a month and are under the age of 30 is 29.949%
   * Acceptance rate of drivers who go to cheap restaurants more than 4 times a month and income is less than 50K is 19.289%
7. Based on these observations, what do you hypothesize about drivers who accepted the bar coupons?
   * Acceptance rate of driver those who went to bar 3 or less times a month is 81.345%, which is higher compare to all other acceptance rate.

**Independent Investigation**

Explore Coffee House coupon groups and try to determine the characteristics of passengers who accept the coupons.

Obervations:

1. Acceptance rate of drivers who go to Coffee House more than 4 times a month, driving alone and before noon accepts coupon 10.137%
2. Acceptance rate of drivers who go to Coffee House more than once a month, driving with a passanger and are under the age of 30 accepts coupon 16.948%
3. Acceptance rate of drivers who Carry out & Take away more than 4 times a month, when the temparature is 80 accepts coupon 30.676%
4. Acceptance rate of drivers who are under the age of 30 and accepts coupon before noon accepts coupon 23.601%
