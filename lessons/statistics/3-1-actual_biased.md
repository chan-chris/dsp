[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

# PMF of actual num kids distribution
numk_pmf = thinkstats2.Pmf(resp.numkdhh,label="actual")
numk_pmf

# Hist of dist
thinkplot.Pmf(pmf)
thinkplot.Config(xlabel='Number of children', ylabel='PMF')

# biased dist
def BiasPmf(pmf,label):
    new_pmf=pmf.Copy(label=label)
    for x,p in pmf.Items():
        new_pmf.Mult(x,x)
    new_pmf.Normalize()
    return new_pmf

biased_pmf=BiasPmf(numk_pmf,label="observed")

# plot actual vs. obs distributions
thinkplot.PrePlot(2)
thinkplot.Pmfs([numk_pmf,biased_pmf])
thinkplot.Show(xlabel='Num Kids per HH',ylabel='PMF')

# print means of actual and obs dist
print('mean actual',numk_pmf.Mean())
print('mean obs',biased_pmf.Mean())
