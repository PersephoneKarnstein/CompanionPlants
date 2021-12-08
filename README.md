# Companion Plant Finder

This code attempts to find companion plants - that is, plants that commonly grow in close proximity to each other - via analysis of iNaturalist data. To do this, it searches for all plants recorded within one km of the target plant, and assigns them a relevance score based on their distance away both from the target plant and from the nearest urban area[^1].

[^1]: The later criterion is because human gardening practice results in unnatural groupings of plants that would not appear in nature, and nominally the further from a population center an observation is, the less likely it is that such will affect growth distributions.

In essence, this creates an ***n x n*** correlation matrix, in which the maximal values identify species with the highest natural coincidence. Companionship is scored using the metric

<center>

![the score as a function of D sub a b; D sub nearest urban; and p sub nearest urban is defined to be the sum over all occurances within a kilometer range of D sub a b to the minus 2 times paren p sub nearest urban over D sub nearest urban close-paren to the minus 1.](CodeCogsEqn.svg)

</center>

where **D<sub>a,b</sub>** represents the distance between the target plant and the potential companion, **D<sub>urban,nearest</sub>** represents the distance to the nearest urban area, and **p<sub>urban,nearest</sub>** represents the population density of that nearest area.