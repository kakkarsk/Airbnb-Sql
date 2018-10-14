# Airbnb-Sql


-  1:  What's the most expensive listing? What else can you tell me about the listing?

SELECT
    
     id,

    name,

    MAX(price) price,

  (minimum_nights) minimum_nights

FROM
    
    listings

GROUP BY 
	
     id,
	
    name,
    
    price,
    
   minimum_nights
   
   
 - 2:  What neighborhoods seem to be the most popular?
 
 Select

	  neighbourhood,

	 count(number_of_reviews)

from

	  listings

Group by

      neighbourhood,

	    number_of_reviews

Order by

	 number_of_reviews
   
-3: What time of year is the cheapest time to go to your city? What about the busiest?

The cheapest time to visit Austin is in March and April.

Select
	
   price,
	
   date1,
	
   available

From
	
   calendar c

Where
	
    available == 't'

Group by
	
    date1

Order by
	
    price
   
 -- The busiest time for AirBnB in Austin is in March - specifically when the SXSW conference is in 
 
 Select
	
   available,
	
   date1,
	
   count(*) as rooms

from
	
   calendar

Where
	
    available = 'f'

Group by
	
    date1

Order by
	
    rooms desc

