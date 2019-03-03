# Exercise 2 #

## Ancient DNA and horse domestication ##
The timing and location of domestication of the ancestors to the present-day domesticated horses remains unknown. The earliest evidence of horse domestication, based on archaeological research, is from a 5,000 year old site named Botai in northern Kazakhstan. Besides the main types of horse breeds living today (e.g. Arabian and Shetland) only a single wild horse lineage is extant, the Przewalski horses. This lineage almost went extinct in the 19th century. Such strong bottlenecks result in large amount of genetic drift due to the decreased population size as demonstrated in exercise 1. 

We will use 20 horse genomes for todays exercise:
- Two ancient horses from Siberia, Russia. These horses represent an extinct horse lineage.
  - The 5,000 years old `AncientRussia1`
  - The 42,000 years old `AncientRussia2`
- 7 Przewalski horses (prefix: `Prze`).
- 4 ancient `Botai` horses (5,000 years old) 
- 7 Present-day domesticated horses from the following breeds:
  - `Japanese`
  - `Mongolian`
  - `Yakutia`
  - `Shetland`
  - `Arabian`
  - `Sorria`
  - `Marwian`
  
For the first analysis, we will also use the `donkey` as an outgroup. 

The ancient siberian horses (`AncientRussia1,AncientRussia2`) are estimated to split of from the branch leading to Przewalski and present-day domesticated horses around 160,000 years ago. The Przewalski lineage and the lineage leading to the present-day domesticated horses split around 45,000 years ago.

Assuming that horse domestication took place only once, our initial hypothesis was that the 5,000 years old domesticated Botai horses were the ancestors of all present-day domesticated horses. In todays exercise, we will investigate if this hypothesis holds by applying two commonly used methods to reconstruct the genetic relationship of the 20 genomes described above.

## Objective ##
The objective of this exercise is to familiarize yourself with two methods, namely f3-outgroup and Treemix. Both these methods are based on genetic drift. Based on the results of these methods, we will investigate if the Botai horses were the ancestors of present domesticated horses.

## f3-outgroup ##
The first method we will apply to the data is named f3-outgroup. This method uses an outgroup (Donkey) to recover the amount of shared genetic drift between two horses/populations. The statistic measures the branch length from the outgroup and split of the two populations. It is defined as the product of allele frequency differences between C-A and C-B [highlighted here in red](https://gaworkshop.readthedocs.io/en/latest/_images/f3-tree.png). 

You will compute all pairwise permutations of the horses analyzed in this study and plot it as a heatmap. The color brightness indicates the amount of shared genetic drfit between two horses. These results can give us the first indication whether the domesticated Botai horses shared more genetic drift with present-day domesticated horses.

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
	
1. Define the two largest monophyletic groups, entailing all samples besides the outgroup (`AncientRussia1,AncientRussia2`). 
   1. What samples are present in each group?
2. Is the placement of the Botai horses expected if they are the ancestors of the present day domesticated horses. Elaborate your answer.
3. What samples shares the most genetic drift the botai horses?
4. Is there a difference between the length of the terminal branches in the two major monophyletic groups?
   1. If yes, explain how and why they differ?
5. Based on this analysis and the f3-outgroup analyses, what group of horses are likely the descendants of Botai horses?

## Extra material ##
These two analyses were a fundamental part of a paper published last year in [Science](http://science.sciencemag.org/content/360/6384/111).
