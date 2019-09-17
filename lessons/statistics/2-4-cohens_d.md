[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

Think Stats Chapter 2 Exercise 4 asks for Cohen's d to investigate whether first babies are lighter or heavier than others, then use that number to compare to the difference in pregnancy length.
Using the code and examples from the book, I solved the problem as follows:

    import nsfg
    
    preg = nsfg.ReadFemPreg()
    live = preg[preg.outcome == 1]
    
    firsts = live[live.birthord == 1]
    others = live[live.birthord != 1]
    
    def CohenEffectSize(group1, group2):
      diff = group1.mean() - group2.mean()
      var1 = group1.var()
      var2 = group2.var()
      n1, n2 = len(group1), len(group2)
      pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
      d = diff / np.sqrt(pooled_var)
      return d
    
    CohenEffectSize(firsts.totalwgt_lb,others.totalwgt_lb)
    
The answer is -0.088672927072602 standard deviations, which is small, although this difference is larger than the difference in mean pregnancy length for firsts vs. others (0.028879044654449883 standard deviations).
The negative value for Cohen's d indicates that the mean pregnancy duration for births other than first is slightly longer than for first births.
