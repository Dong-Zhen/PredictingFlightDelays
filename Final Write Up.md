# Abstract

------------

The Federal Aviation Administration (FAA) estimates that there's a total cost of 33 billion dollars due to air transportation delays in the United States in 2019. The main affected parties are airlines and passengers. A flight is considered delayed after 15 mins from scheduled departure time. The top contributors to delays are **air crarrier, weather, security, and National Aviation System**. 

There's an opportunity **to decrease the costs of delays** because most of the costs are incurred during unforeseen delays. For example airlines could decrease accomodation costs when they let their passengers know ahead of time that there will be a delay so that the passengers could better prepare. If a flight is delayed significantly, passengers have to pay extra for reservations like rental cars and lodging. Passengers also have to pay for food as they get hungry. The airline have to pay for extra crew costs, in the extreme cases they have to hire additional crews. 

As a data scientist, I believe that **training a classification model**  on the top contributors of air transportation delay can predict whether or not a flight will be a delayed departing flight.


------------

### Why delays are costly

When one flight is delayed, it usually has a negative domino effect on the airline’s entire daily flight schedule. As a result, airlines lose billions of dollars annually due to unforeseen delays. 
Airlines incur additional labor costs with delayed flights. Pilots are usually paid based on the greater between scheduled and actual block time, so if the duration of the flight exceeds the actual block time, the airline would have to pay more. They are also responsible for searching for crew members to cover for the scheduled crew if the flight arrives late to the gate.
Additionally, airlines have to provide impacted passengers with travel vouchers if the flight is delayed significantly (3+ hours for Delta) as compensation for the delay. The cost usually adds up to thousands of dollars per fully booked flight! Not to mention, if passengers continue to experience flight delays with the same airline, the chances of them switching to a competitor with better on-time performance increases, which results in lower revenue. 
If the airline continues to arrive late to the gate, their rank for on-time performance will drop to the bottom, damaging the airline’s reputation altogether. 

### Design

To predict the departure delays, I had to design predictive features that were known before a plane departs. The most important features were name of time in day and the minutes delayed by NAS, Delta, and weather affected from the day before. I hypothesized that historical data and time of day would play a crucial part in whether or not there will be a departure delay. Another feature that was important was how many flights a certain plane had scheduled for the day, because the more flights means more turnaround time. Meaning, the aircraft has to go from place to place with less flexibility in schedule.

The rest of the features that I used in the model were from the dataset and scrapped, and that includes the origin airport, the distance travel, computer scheduled time between departing and arriving.

### Data

I scrapped the top 25 airports in 2019 in Wikipedia, and got their regional information. Then used selenium to downloaded air transportation infromation from the Bureau of Transportation Statistics. I created pipelines for this process so that I could have a clean data file to work with for modelling. 

### Algorithmn 

I tried numerous baseline models to figure out which features would provide the best representation of delays. I tried a baseline of just the important features defined by the BTS, minutes delayed by NAS, weather, and air carrier across three models XGboost, Logistic Regression, and Random Forest. Before implementing the features into the models, I split the data into training and test data stratifying the target variable, and then another stratified split to get training and validation sets. 

I performed cross validation scoring for both precision and recall across all models. The results were low for both precision and recall for Logistic Regression. Precision was performing relatively well above 70% for random forest and XGboost, however they had a recall of less than 4%. 

I tried regional features expecting that the models would generalize better and increase recall, however it actually decressed precision to an average of 55% instead and recall remained the same. 

### Conclusion

For my final model I used a random forest that had both regional and flight features that made had an average precision score of 75% and recall score of 1%. This will not be used as a predictive model for Delta. Instead it is a good interpretative model to find features of future study like regional weather data, that can improve the model where it wil be sufficient for predicting departure delays.

In the future I want to look deeper for weather, nas, and air carrier data.

### Links

- [Final Code](https://github.com/Dong-Zhen/PredictingFlightDelays/tree/master/Code)
- [Presentation](https://github.com/Dong-Zhen/PredictingFlightDelays/blob/master/Flight%20Delays.pdf)
- [Write Up](https://github.com/Dong-Zhen/PredictingFlightDelays/blob/master/Final%20Write%20Up.md)



