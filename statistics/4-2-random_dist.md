[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

First, I will set a variable to the random distribution of values from 1-1000:

```
t = np.random.random(1000)
```

Then, I will plot a pmf, though I suspect the CDF will be more helpful:

```
pmf = thinkstats2.Pmf(t)
thinkplot.Pmf(pmf, linewidth=0.1)
thinkplot.Config(xlabel='Random variate', ylabel='PMF')
```

The pmf visualization was not helpful at all, here is the CDF code:

```
cdf = thinkstats2.Cdf(t)
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel='Random variate', ylabel='CDF')
```

This showed a nearly straight line with normal distribution, indicated that this range is indeed random.