# CitiBike NYC
![NYC](./images/header.png)

## Overview
After a 2-week trip to New York City, and many hours using CitBike bikes to take in the world-famous sites, 2 friends decided to explore the possibility of starting a similar bike sharing company in their home town of Des Moines, Iowa. 

Looking to secure funding from a potential angel investor, the friends need to do some research.  With the help of data secured from CitiBike NYC for the month of August 2008, they need to dive in and learn what they can about the operations and the potential for DM BikeShare.

Despite the limitations of the data (i.e. one month's time of a city with a much different profile than Des Moines, no pricing or cost information), much can be learned for this data.

**Raw Data:** 
The csv flatfile contains 2,344,224 lines of data with the following fields:

* Tripduration: ***updated via Python (Pandas) to convert to Date/Time***
* Starttime
* Stoptime
* Start Station Id
* Start Station Name
* Start Station Longitude
* Start Station Latitude
* End Station Id
* End Station Name
* End Station Longitude
* End Station Latitude
* BikeID
* Usertype
* Birth Year
* Approx. Age: ***calculated field: 2008 - Birth Year*** 
* Gender
* Gender2: ***calculated field to convert 0, 1, 2 values to the tags: 'Unknown', 'Male', 'Female'***
* Tripdur Orig: ***original trip duration data (in second)***
* Trip Duration in minutes: ***calculated field***
* Approx. Age (bin): ***calculate field based on Approx. Age***

Tools utlizied include Python (Pandas) to convert ```Tripduration``` to a Date/Time Stamp and Tableau Public to create the visualizations presented below.

## Results
The fundamental purpose of this analysis is to understand aspects of the CitiBike NYC operations to uncover potential for recreating it in Des Moines, Iowa.  Three primary areas of focus for analysis answers the questions:

1. Who is buying the services; who are the **users** of the service?
2. What is the anatomy of the service (i.e. **product**); typical ride times, cadence of demand
3. How the capital investment of bicycle **inventory** is utilized and moves through the system.


### Customer Profile
For the month of August in 2008, CitiBike NYC customers are:

1. **2.5X more likely to be men** (65%) than women (25%)
2. **81% of the volume** (i.e. number of trips) comes from **Subscribers** vs off-the-street Customers: 80/20 rule.
3. Of those **subscribers, 59% are men**; again almost 3X the number of female subscribers (21%)
4. The majority of trips taken by a rider with a **gender "unknown"** are coming from **off-the-street Customers**, not Subscribers.
5. Not surprising, male Subscribers are the heaviest users during the work week: ***commuters***.
6. Teenagers (10 - 20 years old) are the highest age-group consumer, with the 20- and 30-year olds not too far behind.  As the age advances, the demand for this service decreases (inverse relation). 


![customer](./images/customers_citibike.png)
Understanding the ages groups and the genders of the heaviest users will help guide the purchase of the largest capital investment of the bicycles themselves.  

Understanding where the demand occurs (outside public transportation for commuters vs sightseeing attractions or trails for recreational users) will guide where to establish station locations.

Understanding the customer profile will guide how and where to advertise to create demand.

### Trip Profile
What does a typical ride or trip look like?  How long? What time of day? What type of rider? How many trips per month?

Based on this limited data, we can see:

* The heaviest demand for the service occurs: 
	* during **weekday morning and afternoon rush hour**: 6 AM to 9 AM and then again 4 PM to 8 PM,
	* on **Saturday** (more so than Sunday): late morning through evening hours (10 AM to 8 PM).

* Again, no surprise that significantly more of these trips are taken by men versus women, but what is telling is that it appears the "unknown" gender are more often recreational riders as there is more use of service on Saturdays. 

**Please note:** the trip volume is very high: over **2.3 million trips** during high tourist season in August 2008. Population difference between NYC and Des Moines is vast: 8 million (NYC) vs 200,000 (DM) in 2008.  On the tourist front, no city is more visited than NYC.

This level of volume is not realistic for the small city of Des Moines and unfortunately, *without pricing or cost information it is difficult to understand profitability break-even points based on different levels of volume*

![trip](./images/trip_citibike.png) 

* The length of Trip in terms of time (i.e. Checkout Time), shows the most common trip duration is about **5 hours** and male Users are more likely to have the bikes out longer than female Users.

* Looking at the **average trip duration in minutes**, the average trip is longest in terms of time for 30-40 year-olds and children 0-10 years-old, which suggests recreational rides of parents with their children.  

* Finally, the data suggests the average trip duration for a Subscriber is less than half that of a Customer.  

All of these findings underscore there are 2 very distinct uses for this service and as such plans for pricing, inventory types and levels, and marketing rely on this information.

![trip](./images/trip_citibike2.png)

**DISCLAIMER**: any visualization depicting age, uses approximate age based on number of years from birthdate to 2008.  Any birthday resulting in an age over 100 years-old was eliminated from the visualization.

### Inventory
With the inventory of bicycles in constant movement, it is important to understand instances where the demand for the service is occurring at location A at time A but the bikes have been returned to location B at time B, causing a shortfall in one area and a surplus in another.

* Starting with the **Peak Hours for starting and ending trips**: the number of trips that start and stop occur within the same hour for the most part.  *This speaks to the fact the average trip duration is well within the hour time frame.*

![inventory](./images/inventory_citibike.png)

* Pulling the top 30 Start Locations (where demand is high) and the top 30 End Locations (inventory is returned), it appears that with some exception, **a comparable number of bicycles are being returned to the top Starting locations**.

![inventory](./images/inventory_citibike2.png)

While this speaks to number of trips (i.e. bicycles in use), it does not capture the percentage or number of trips where the specific bike (i.e. BikeID) is being returned to the same Station. 



The full presentation can be found on Tableau Public:  [CitiBike NYC August 2008 Presentation](https://public.tableau.com/profile/maggie.mcphail#!/vizhome/CitiBike_Challenge_16099827424670/Story1?publish=yes)


## Summary
Ironically, the demand that drives the volume for NYC CitiBike, subscribers/commuters, is not the user experience these 2 friends had that inspired them to explore the possibility of replicating the bike share company.  If their plan was to focus on the tourism and recreational uses for the service, this data suggests they would not be poised for success.

In summary:

* It is clear that **the operation of CitiBike NYC heavily relies on the subscription model**; and currently the **target age group market appears to be Young Adult to 40-year-olds**. 

* There appears to be little issue with inventory of bicycles moving from one geographic area to the other; causing a need to transport bikes from a popular ending destination back to a starting destination.

### Next Steps
For deeper analysis, the cost and pricing structure needs to be layered into the existing data.  Additional visualizations could include:

* Revenue by User Type: *does the 80/20 rule still exist?* 
* Average Cost per Bicycle by Average Price per Trip: *how many trips needed to cover inventory investment?*




