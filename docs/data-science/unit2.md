# Data Processing

## Discrete & continuos random variable

random variable ($$X$$): variable whose values are numerical outcomes of random phenomenon.

- discrete
- continuos

discrete random variable

- take only countable number of distinct values (eg 0,1,2,3..)
- eg: no. of children in family
- defective light bulb in box

`probability distribution`| mass function | probability function:list of probabilities associated with each possible values

- random variable $$X$$ may take $$k$$ different values, with the probability that $$ X = xi$$ defined to be $$P(X=xi) =pi$$.
  - where $$0<=pi<=1$$
  - $$p1+p2+p3+...+pk=1$$

Continuous Random Variable

- one which takes an infinite number of possible values.
- usually measurements
- eg: height,weight , amount of sugar in an orange
- defined over an interval of values, represented by `area under curve`
- probability of observing any single value is 0.
- since, number of values which may be assumed by random variable is infinite

suppose random variable $$X$$ may take all values over an interval of real numbers.

- probaility that $$X$$ is in set of outcomes $$A$$ ,$$P(A)$$
- $$P(A)$$ is defined as : area above A and under a curve
- curve :represents function $$p(x)$$ must satisfy
  - the curve has no negative values $$p(x)>=0 for all x$$
  - the total area under the curve is equal to 1
- curve meeting these retirements known as density curve

## Missing values

- when no data value is stored for variable in an observation
- can give significant effect on conclusion
- can bias the results or reduce accuracy

### Why data missing from dataset

- reasons for missing data affect approach of handling missing data.
- past data might get corrupted due to improper maintenance
- observation is no recorded
- might get failure in recording values (human error)
- user not provide values intentionally

### Types

![types of missing values](2022-10-18-14-18-01.png)

- missing completely at random 
- missing at random 
- missing not at random

