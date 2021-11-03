# Camp Nou SmartBooking
Predictive model and seat allocation algorithm at Camp Nou.  
[🗞️ Press release](https://www.fcbarcelona.com/en/news/981315/fc-barcelona-promotes-an-intelligent-ticket-sales-model)
[💼 Partner Agency] (https://www.basetis.com/en/exito/smart-booking-increase-ticket-sales-thanks-capacity-forecast/)

# Table of contents
1. [Introduction](#introduction)
2. [Problem](#problem)
3. [Solution](#solution)
4. [Data](#data)
5. [Results](#results)


## 1. Introduction <a name="introduction"></a>
The stadium capacity of a top-level sports club is generally reserved for its members. With a capacity of 99,354, Camp Nou is the biggest stadium in Europe. About 90,000 of those stadium seats, are owned by members for the entire season and who on many occasions do not attend matches for different reasons. In order to avoid empty seats on a match day, the Club has created an official system –called Seient Lliure– as a platform for members to free up/release their seat and recover 50% of its value. Now they can decide to release their seat at any time before the game in order to sell it. So, the benefits are shared between the member and the club.

<img src="https://user-images.githubusercontent.com/4792886/132962391-aa9ab65c-955f-4166-a145-63800333ea55.png" alt="alt text" width="300">


## 2. Problem <a name="problem"></a>
Currently, on average 37% of the seats for matches at the Camp Nou are released in the last 72 hours before the match. Consequences are:
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
- Maximize ticket sales thanks to the capacity forecast, knowing how many members will free their seats and in which area. In this way, it is possible to sell tickets in advance regardless of when the members release them.
- An application of Dynamic Pricing strategies due to a higher timespan for commercialization.
- Unlock the opening of cross&up-selling and new sales channels (through APIs) by being able to bridge the LaLiga systems.


The following diagram shows the ticket sales and seat assignment flow:

<img src="https://user-images.githubusercontent.com/4792886/132963245-e152c0b5-7e8b-44f3-84f6-5eec09e9892c.png" alt="alt text" width="1500">


## 4. Data <a name="data"></a>
I. Model features

| Match profile                   | Opponent                        | Sales and stock                 | Members and zones               | 
| -------------                   | -------------                   | -------------                   | -------------                   |
| Time, Day, Month                | Distance in points              | Local sales                     | # Releases top limit            |
| Season of the year              | Goals for and against           | Seat release curve              | Avg. releases by zone           |
| Competition                     | Last results                    | Ticket prices                   | Members classification by zone  |
| Match Day #                     | Elo Ratings**                   |                                 | Member seniority                |
| Competition Winner (Un)Known    | Trophies                        |                                 | Zone                            |   
| Special Event*                  | # Seasons in the League         |                                 | Member to Club seats ratio      |
| Days left to match              | Sympathy for opponent           |
| Days available for seat release | Derby                           |

*Player's retirement, Title Celebration
**[The case for Elo ratings](http://clubelo.com/TheCase)

| Weather                         | External Factors                | Web and app                     |
| -------------                   | -------------                   | -------------                   |
| Rainfall                        | Holidays                        | Navigational data from locals   |
| Wind                            | Holiday 'bridges'               | Users classification            |
| Storm                           | Special days                    | Match Popularity Index          |

II. Historical data from the last five seasons

## 5. Results <a name="results"></a>

· 10% More tickets sold during the season
· 41% Increase in the average ticket value
