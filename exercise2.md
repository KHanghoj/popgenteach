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
	cd xxx
	# This will generated all the pairwise permutations of the horses analyzed in this exercise
	bash scripts/run_f3.sh
	# This produce a heatmap of the f3-outgroup statistic
	Rscript scripts/plot.f3.simple.R results/f3.results labels/f3.order
	
```


### Questions ###

	1. Why are the f3-outgroup values so high for Przewalski horses.
	2. What are the main groups of horses that share more within populations genetic drift
	3. What Horses share the most drift with Botai horses?
	4. Does these results indicate that Botai horses are the direct ancestors of the domesticated horses we know today?
	   1. If not what does the results then indicate?


## Treemix ##

In this exercise, every populations consists of a single individual.


