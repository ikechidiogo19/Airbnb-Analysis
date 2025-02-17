# Airbnb Analysis
### Project overview
This project provides an in-depth analysis of Airbnb listings, exploring trends, pricing patterns, and host behaviors to uncover valuable insights for stakeholders.

### Data sources

### Tools Used

- Postgresl sql - Data cleaning and Data analysis
- Power bi - Data Visualization

### Data Cleaning/Preparation 

In the data preparation phase we performed the following tasks:
1. Data loading and inspection
2. Handling missing Values.
3. Data cleaning and formatting.

### Exploratory Data analysis

1. What is the distribution of verified hosts versus non-verified hosts?
2. How do listings' prices vary across different neighborhood groups and countries?
3. What room types are most common and how do their prices compare?
4. How does the instant bookable feature affect the number of bookings or reviews?
5. How does the cancellation policy impact the booking rates and reviews?
6. What factors influence the number of reviews and review ratings?
7. How do minimum nights requirements impact the pricing and booking frequency?
8. How does the construction year of the property affect its price and booking rates?
9. Are there specific neighborhoods that perform better in terms of and reviews?

### Data analysis
include some interesting code/features worked with

``` SQL
select *
from bnb
where neighbourhood_group = 'Bronx';
```
``` SQL
-- Distribution of verified and unverified host
select host_identity_verified,count(host_identity_verified)
from bnb
group by host_identity_verified;
```
``` SQL
--How do listings prices vary across different neighborhood groups?
select distinct neighbourhood_group, count(price) AS Listing_prices
from bnb
group by neighbourhood_group
order by Listing_prices desc;
```
``` SQL
-- How does the instant bookable feature affect the number of reviews?
select instant_bookable, sum(number_of_reviews)
from bnb
group by instant_bookable
```
``` SQL
--How does the cancellation policy impact the reviews?
select cancellation_policy, count(number_of_reviews) AS no_of_reviews
from bnb
group by cancellation_policy
order by no_of_reviews desc ;
```

### Results/Findings
The analysis results are summarized as follows:

1. The analysis indicates that the distribution of hosts is almost equal, with verified hosts totaling 50.14K and unverified hosts at 50.23K.
2.  Listing prices by neighborhood groups show that Manhattan and Brooklyn have the highest prices, at 43K and 41K respectively, while Staten Island has the lowest at 3K.
3.  In terms of reviews, the neighborhoods of Bedford-Stuyvesant, Williamsburg, and Harlem received the most, whereas Crown Heights and East Harlem have the fewest.
4.  The analysis also mentions the impact of the Instant Bookable feature on earnings, noting that the difference is minimal, with earnings being 1.374M for listings with the instant bookable feature and 1.367M for those without.
5. price trends by construction year show peaks around 2010 and 2015, with a stabilization observed post-2020.

### Recommendations
Based on the analysis we Recommend the following actions:
- The analysis suggests that enhancing the guest experience by addressing their concerns would improve ratings.
- promoting underperforming areas to increase visibility for neighborhoods with fewer reviews.
- The convenience of Instant Booking feature should be highlighted to increase its adoption.
- Lastly, the analysis advised targeting properties built after 2015 for better pricing stability.

### Limitations
I removed all rows that had missing values


