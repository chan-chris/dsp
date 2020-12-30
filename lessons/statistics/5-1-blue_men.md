### [Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

### How many people are between 5'10" and 6'1"?

#### setup parameters of height
```
lowft=5
lowinch=10
hift=6
hiinch=1
```
#### convert to cm
```
lowcm=( (lowft*12*2.54) + (lowinch*2.54))
hicm=( (hift*12*2.54) + (hiinch*2.54))
```
#### print range of height cm
```
print(lowcm,hicm)
```
177.8 185.42
#### obtain probability below threshold
```
locdf=dist.cdf(177.8)
hicdf=dist.cdf(185.42)
```
#### print results
```
print("low CDF:",locdf,"high CDF:",hicdf,"between CDF:",hicdf-locdf)
```
low CDF: 0.48963902786483265 high CDF: 0.8323858654963063 between CDF: 0.3427468376314737
