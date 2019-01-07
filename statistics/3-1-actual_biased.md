[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

##Code
For this solution, we can first set a variable "Pmf" equal to a distribution of the NSFG variable "numkdhh", and then use the function the author has already defined, "BiasPmf", to create a biased distribution ("biased"). We can then use the thinkplot.Pmf() function to plot distribution as a step function, to compare the two distributions. Finally, you can use the standard mean() function to calculate the means of each:

```
resp = nsfg.ReadFemResp()
pmf = thinkstats2.Pmf(resp.numkdhh, label='numkdhh')
biased = BiasPmf(pmf, label='biased')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased])
thinkplot.Config(xlabel='Number of children', ylabel='PMF')
pmf.Mean()
biased.Mean()
```

