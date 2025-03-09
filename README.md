# Sportbook-Arbitrage
Strategy attempts to take advantage of line mispricing across sportsbooks. This code aims to (1) identify mispricings, (2) calculate optimal allocation, and (3) place bets across multiple books. 

## Strategy  
Suppose we have a tennis match between Nate and Amy with the following odds from different books: 
*  Nate - 2.10 (book 1)
*  Amy - 2.05 (book 2)
  
To calculate implied probabilities from odds, we do the following:
*  Nate: 1/odds -> 1/2.1 = 0.476
*  Amy: 1/2.05 = 0.488

Note that for this event, there are only two possible outcomes. But when we sum the implied probabilities together, we get: 0.476 + .488 = 0.964 < 1! Thus, an arbitrage opportunity exists (1). 

Assuming that we have $100 to bet, we decide the stake (2) as follows: ([bankroll] * [outcome_i odds])/[total odds]
*  Nate : 100 * (.476/.964) = 49.378
*  Amy : 100 * (.488/.964) = 50.622

To find our profit, we do the following: 
* Nate : 49.378 * 2.10 = 103.694
* Amy : 50.622 * 2.05 = 103.775

Thus, for a $100 stake, our strategy makes a guarenteed profit of at least 103.69, and a max of 103.78.
