[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

What percent of the male US population is between 5'10" and 6'1"?

```
import scipy.stats
mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)
low = dist.cdf(177.8)
high = dist.cdf(185.4)
diff = high-low
```
diff = 0.3420946829459531
