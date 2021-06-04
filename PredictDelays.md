# Abstract

------------

The Federal Aviation Administration (FAA) estimates that there's a total cost of 33 billion dollars due to air transportation delays in the United States in 2019. The main affected parties are airlines and passengers. A flight is considered delayed after 15 mins from scheduled departure time. The top contributors to delays are **air crarrier, weather, security, and National Aviation System**. 

There's an opportunity **to decrease the costs of delays** because most of the costs are incurred during unforeseen delays. For example example airlines could decrease accomodation costs when they let their passengers know ahead of time that there will be a delay so that the passengers could better prepare. If a flight is delayed significantly, passengers have to pay extra for reservations like rental cars and lodging. Passengers also have to pay for food as they get hungry. The airline have to pay for extra crew costs, in the extreme cases they have to hire additional crews. 

As a data scientist, I believe that **training a classification model**  on the top contributors of air transportation delay can predict whether or not a flight will be a delayed departing flight.


------------



## Why delays are costly

Airlines lose money due to **schedule buffers and unforeseen delays.** Pilots are usually paid based on the greater of scheduled and actual block time. Airline fleet and crew workers have to wait for delayed planes to arrive resulting in additional labor costs. The airline's schedule and fleet must respond to delays resulting in additional aircrafts and other inconveniences. The airline's reputation is in risk of being damaged which requires airlines having to accomodate passengers. 

Passengers lose money because of **unforeseen delays**. They have to pay extra for earlier flights to avoid delays or they pay to change fligths when airlines adjust their schedules because of delays. Some passengers are late to important business meetings because of delays. 

## Data Sources

I will be using data from the Federal Aviation Administration, the Bureau of Transportation Statistics, and Weather Data. The focus is on Delta flights departing from the top 10 U.S. airports. 

Questions: 

1. What are the contributors to airplane delays?  
2. How does weather affect delays?
3. Does time of day play a factor?

## Problem

Airlines and passengers in the U.S. are incurring billions of dollars in lossses annually form flight delays. How can Delta decrease these losses for unexpected flight delays?
<!--more-->


## Desired Impact

Reduce the costs for Delta and their customers caused by unforeseen delays. 

**Impact Hypothesis:** The costs incurred by unforeseen delays can be reduced by predicting which Delta flights have a higher chance of being delayed  in order for Delta to alert their customers and to better prepare for the delay. 

## Data Solution 

Use classification to identify which flights will be delayed using weather, nas, security, and potentially time features. 


