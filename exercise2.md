# Exercise 2 #

## Ancient DNA and horse domestication ##

Number of samples
where they are from

relationship 

expectation

In exercise 2 we will investigate if the botai horses are the ancestors of present day domesticated horses. To unravel this we will use two different methods, namely f3-outgroup and treemix. Both methods are based on genetic drifts. 


## Objective ##
The objective of this exercise is to familiarize yourself with two methods, namely f3-outgroup and Treemix. Using these methods, we will investigate if the Botai horses were the ancestors of present domesticated horses.

## f3-outgroup ##
The first method we will apply to the data is named f3-outgroup. This method uses an outgroup (Donkey) to recover the amount of shared genetic drift between two horses/populations. The statistic measures the branch length from the outgroup and split of the two populations. It is defined as the product of allele frequency differences between C-A and C-B [highlighted here in red](https://gaworkshop.readthedocs.io/en/latest/_images/f3-tree.png). 

You will compute all pairwise permutations of the horses analyzed in this study and plot it as a heatmap. The color brightness indicates the amount of shared genetic drfit between two horses. These results can give us the first indication whether the domesticated Botai horses were the direct ancestors of present-day domesticated horses.

```bash
	cd XXX
	# This will generated all the pairwise permutations of the horses analyzed in this exercise
	bash scripts/run_f3.sh
	# This produces a heatmap of all the pairwise f3-outgroup statistics
	Rscript scripts/plot.f3.simple.R results/f3.results labels/f3.order
```

### Questions ###

	1. Why are the f3-outgroup values so high for all pairs of Przewalski horses.
	2. What are the main two groups of horses that share more genetic drift?
	   1. Are these groups of horses expected given our expectation?
	3. What Horses share the most drift with Botai horses?
	4. Does these results indicate that Botai horses are the direct ancestors of the domesticated horses we know today?
	   1. If not, what does the results then indicate?


## Treemix ##
    The second method is named `treemix` and is used to reconstruct the genetic relationship between populations based on genetic drift. In this part you will generate an evolutionary tree using `treemix` of the same subset of horses as used in the previous analyses with the exception of the outgroup. Instead of using the donkey as outgroup, we use `AncientRussia1` and `AncientRussia2` in this analysis. These two samples represent a wild horse lineage that went extinct around 5,000 years ago and is suitable as outgroup. 

Every populations in this exercise consist of a single individual. Vertical lines do not have any biological meaning. 


```bash
	# This script will run a two commands. The first will transform the data into the required format for Treemix. The second command is the actual treemix command.
	bash scripts/treemix_run.sh
	# Next we plot the treemix results. 
	Rscript scripts/plot.treemix.R results/treemix
```

### Questions ###
	Based on the treemix plot saved in `results/treemix.pdf` answer the following questions.
	
	1. Define the two main monophyletic groups in addition to the outgroup (`AncientRussia1,AncientRussia2`). 
	   1. What samples are present in each group?
	2. Is the placement of the Botai horses expected if they are the ancestors of the present day domesticated horses.
	3. What samples shares the most genetic drift the botai horses?
	4. Is there a difference between the length of the terminal branches in the two major monophyletic groups?
	   1. If yes, explain how and why they differ?
    5. Based on this analysis and the f3-outgroup analyses, what group of horses are likely the descendants of Botai horses?
	
	


