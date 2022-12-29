### Trading Strategy Implementation with Broker

Idea of strategy is to capitalise on the inverse relationship between futures A and futures B. As futures B decreases past a threshold, we enter a positoin in futures A and vice versa.

Strategy Overview:

- Buy or maintain a long position of size L>0 in futures A every time the price of futures B falls more than X sd average in a day
- Sell or maintain a short position of size S<0 in futures A every time the price of futures B rises more than Y sd average in a day
- Close any posiitons if neither condition is met
- The sd is calculate over previous N days
Coding Implementation overview:

- The class 'strategy' implements the trading strategy to output a set of 'buying conditions'. We then get the indicies where we would like to enter and exit our positions

- The class 'portfolio' implements takes the indicies that have been generated and uses this information to buy and sell futures A and also generate results from this strategy.

- Note that the code generates REALISED pnl.

- We use degrees of freedom 1 when computing the standrard deviation since we are sampling from a larger distribution