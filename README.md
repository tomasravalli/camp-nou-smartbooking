# Camp Nou SmartBooking
Predictive model and seat allocation at Camp Nou.


# Table of contents
1. [Introduction](#introduction)
2. [Problem](#problem)
3. [Solution](#solution)
4. [Data](#data)
5. [Future Improvements](#futureimprovements)


## 1. Introduction <a name="introduction"></a>
With a capacity of 99,354, Camp Nou is the biggest stadium in Europe. About 90,000 of those stadium seats, are owned by members for the entire season and who on many occasions do not attend matches for different reasons. In orfer to avoid empty seats on a match day, the Club has created an official system –called Seient Lliure– as a platform for members to free up/release their seat and recover 50% of its value.

<img src="https://user-images.githubusercontent.com/4792886/132962391-aa9ab65c-955f-4166-a145-63800333ea55.png" alt="alt text" width="300">


## 2. Problem <a name="problem"></a>
Currently a high percentage of the seats for matches at the Camp Nou are released in the last 72 hours before the match. Consequences are:
- As there are hardly any releases by members at the time a match goes on sale, there are hardly any tickets available. Additionally, it is highly unlikely to have seats available in pairs, making sales even more difficult. Other competing secondary ticketing sites, such as Viagogo, do offer seats in pairs.
- Match after match there is a high proportion of unsold seats left, showing an inconsistency between the real demand to attend a Camp Nou match and the final attendance reflected in the stands.
- Specially for matches in the second half of the season, there had not been seats available until 2-3 days before the match.

The following fictional match serves as an example of what happens repeatedly on a typical season:

i. In -61 days (prior to the match) the available seats go on sale. This stock (8,600) is sold almost entirely in 6 days.
ii. Between -55 and up to -10 days there is hardly any availability. The sale is closed waiting to have more seats, specially in pairs.
iii. At -9 days, the accumulated stock of 'released seats' go on sale, having a sales peak similar to that of the sales opening.
iv. The last 3 days there is a peak of releases from members, but the demand can no longer absorb all of the stock.
v. An accurate prediction would have adviced to go on sale with a total of 25,000 (virtual) seats.

<img src="https://user-images.githubusercontent.com/4792886/132962984-fb1e94f5-993d-48a9-8eee-fba4b9fc41f1.png" alt="alt text" width="700">


## 3. Solution <a name="solution"></a>
SmartBooking is the project conceived to solve the current problem. Its 3 main axes are:
- Ticket sales by zones, before the seats are released, using a match-by-match predictive model of “Seient Lliure”. The sale is therefore made without confirming the exact location (row and file). Similar to airlines.
- Optimization of the sold seats stock: the prediction will guarantee pairs of seats in all areas of the Stadium.
- Reliability: The customer will always have the tickets in the area indicated when making the purchase. Seat assigment will be confirmed 48 hours before the match.

SmartBooking business objective is to increase ticketing revenue as a consequence of:
- An alignment between the Offer and the Demand at the moment in which the latter occurs.
- An application of Dynamic Pricing strategies due to a higher timespan for commercialization.
- Unlock the opening of new sales channels (APIs) by not having to connect to the LaLiga system.

The following diagram shows the ticket sales and seat assignment flow:

<img src="https://user-images.githubusercontent.com/4792886/132963245-e152c0b5-7e8b-44f3-84f6-5eec09e9892c.png" alt="alt text" width="1500">


## 4. Data <a name="data"></a>


## 5. Future Improvements <a name="futureimprovements"></a>

### Prediction
The prediction system can be improved in the following ways:
- Performance: the acceleration of the execution of the predictive algorithm should be explored, with the study of its potential parallelization. This will allow multiple predictions to be run more times and concurrently as to have different prediction scenarios.
- Risk management: overbooking risk management can be improved introducing margins of error in predictions, using Bayesian statistics or probabilistic programming.
- Data augmentation: the inclusion of new microscopic variables will be explored variables to the model, especially those that facilitate the micro-forecast of seats. These variables refer especially to demographic data of members, their history  and the use of the app "Seient Lliure".
- Accuracy: efforts can be made to improve release prediction, be it testing new algorithms or fine-tuning existing ones whenever possible.

### Allocation
The allocation algorithm is the most critical in the system, and in the short term, it can be improved in the following aspects:
- Optimization mechanisms: It is possible to consider the improvement of the optimization algorithm to increase the quality of the assignments, for example through linear or conical programming (CVXPY, OR-tools) or Simulated Annealing, frequently used in theory of graphs.
- Partial upgrades and rejections: the allocation algorithm must be modified to allow manual and partial upgrades, as well as potential rejections, without having to recompute the entire process from scratch.
- Adaptation for the VIP algorithm: since the VIP service has a differentiated audience, the allocation priorities are different. For this reason, the objective (the quality function to be optimized) must be changed and adapted to this case.
