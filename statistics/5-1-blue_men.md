[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

To answer this question, we need to import scipy.stats, and set some variables for mu, sigma, and set a normal distribution:

```
import scipy.stats
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)
```

We can then use dist.cdf() to calculate the amount of people between 5'10" and 6'1":

```
low = dist.cdf(177.8)    # 5'10"
high = dist.cdf(185.4)   # 6'1"
high-low
```

high-low here returns a value of 0.3420946829459531, which is our answer (~34%)