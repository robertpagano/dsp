[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

#Cohen's D Exercise Solution

##Setup and importing
The first thing I did to solve this problem was to create a new Jupyter notebook, and import everything I needed. I imported first (to make it easier to pull in the data frames) and thinkstats2

##Creating a function
I then created a function that would take in 3 data frames - all live births, first births, and then any other births. This function would calculate the means of all 3 dataframes, and then the variance of the first births and other births separately. These were to get an overall glimpse at some different summary statistics to include with Cohen's D. At the end of the function, Cohen's D is calculated using Allen Downey's built in function 'CohenEffectSize'

```
def WeightDifference(live, firsts, others):

    mean0 = live.totalwgt_lb.mean()
    mean1 = firsts.totalwgt_lb.mean()
    mean2 = others.totalwgt_lb.mean()

    var1 = firsts.totalwgt_lb.var()
    var2 = others.totalwgt_lb.var()

    print('Mean')
    print('First babies', mean1)
    print('Others', mean2)

    print('Variance')
    print('First babies', var1)
    print('Others', var2)

    print('Difference in lbs', mean1 - mean2)
    print('Difference in oz', (mean1 - mean2) * 16)

    print('Difference relative to mean (%age points)', 
          (mean1 - mean2) / mean0 * 100)

    d = thinkstats2.CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
    print('Cohen d', d)
```

When this function is run, given the aforementioned dataframes as params, these values were printed:

```
Mean
First babies 7.201094430437772
Others 7.325855614973262
Variance
First babies 2.0180273009157768
Others 1.9437810258964572
Difference in lbs -0.12476118453549034
Difference in oz -1.9961789525678455
Difference relative to mean (%age points) -1.7171423678372415
Cohen d -0.088672927072602
```

The difference in means, as shown above, seems insignficant to me. It is only ~.09 standard deviations difference between the two means.