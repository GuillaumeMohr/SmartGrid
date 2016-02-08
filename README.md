# SmartGrid
Smart(ish) parameter search for scikit-learn

## Objective
This is a simple tool that I use to automate parameter search with [scikit-learn](http://scikit-learn.org/) 
classification algorithm. It is a kind of randomized grid-search but each iteration affects the probability of drawing
a set of parameters in the future.  


Specifically :

0. for each parameter of interest, we discretize the search space (depending on the precision we wish to have)
1. we start with a uniform distribution
2. we draw a parameter set and evaluate the score (with cross-validation)
3. we modify the distribution so that (i) the probability of drawing the same parameter set is zero, 
(ii) the probability of drawing a parameter set next to it is reduced (more or less drastically according to the relative
value of the score : a low score will significantly reduce the probability of drawing another set next to it)
4. we repeat starting from 2. until a fixed number of steps is reached (or all the possible parameters sets have 
been evaluated).

## API
...
