[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

In this exercise, I was asked to look at the NSFG data and compare actual vs. biased distributions of the number of children under 18 in respondents' households. I worked through the problem using the code from Think Stats 2.

    import nsfg
    import first
    import thinkstats2
    import thinkplot
    
    resp = nsfg.ReadFemResp()
    pmf_actual = thinkstats2.Pmf(resp.numkdhh, label='actual')
    pmf_biased = BiasPmf(pmf_actual, label='biased')
    
    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf_actual, pmf_biased])
    thinkplot.Show(xlabel='Number of Children', ylabel='PMF')
    
![Plot of Actual vs Biased PMFs of number of children in respondents' households](https://github.com/ehillenbrand4541/dsp/blob/master/img/ch03ex01plot.png)

Then, I computed the mean of each distribution and compared them:

    print('Actual mean: {}'.format(pmf_actual.Mean()))
    print('Biased mean: {}'.format(pmf_biased.Mean()))
    print('Biased mean is {} times greater than Actual mean.'.format(pmf_biased.Mean()/pmf_actual.Mean()))
    
Actual mean: 1.024205155043831

Biased mean: 2.403679100664282

Biased mean is 2.3468726834922213 times greater than Actual mean.

