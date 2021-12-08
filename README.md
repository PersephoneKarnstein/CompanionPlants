# Readme

This code attempts to find companion plants - that is, plants that commonly grow in close proximity to each other - via analysis of iNaturalist data. To do this, it searches for all plants recorded within one km of the target plant, and assigns them a relevance score based on their distance away both from the target plant and from the nearest urban area[^1].

[^1]: The later criterion is because human gardening practice results in unnatural groupings of plants that would not appear in nature, and nominally the further from a population center an observation is, the less likely it is that such will affect growth distributions.

In essence, this creates an ***n x n*** correlation matrix, in which the maximal values identify species with the highest natural coincidence. Companionship is scored using the metric

<center>

![doop](CodeCogsEqn.svg)

</center>