# Exercise 1 #

## genetic drift ##
In this exercise, we will explore the effect of genetic drift on allele frequencies using simulations. The web-based software we will use is named `driftR`. It simulates change in allele frequencies for multiple popoulations using the island model (Wright 1931).

## Objective ##
The objective of this exercise is to familiarize yourself with genetic drift, and explore the effect of populations size on genetic drift.

## Installing driftR locally ##

Run the following command to download driftR to your local machine:
```bash 
	git clone https://github.com/cjbattey/driftR.git
```

Open `R` and run the following code:

```R
	ipak <- function(pkg){new.pkg <- pkg[!(pkg %in% installed.packages()[, "Package"])]
		if (length(new.pkg))
			install.packages(new.pkg, dependencies = TRUE)
		sapply(pkg, require, character.only = TRUE)
	}
	ipak(c("shiny", "viridis", "reshape", "ggplot2", "plyr", "magrittr"))
	pathTodriftR <- "driftR"
	runApp(appDir=pathTodriftR)
```

This should open your favorite browser with driftR running locally. 


### Alternative availability (on the student server) ###
If it is not possible to install driftR locally, a version is made available on the server. X11 forwarding is required, when you access the student server. Open `R` and type the following:

```R
	require(shiny)
	pathTodriftR <- "/path/to/driftR"
	runApp(appDir=pathTodriftR)
```

### Starting parameters ###
This software has a series of parameters to tune. Set the following parameters prior to running driftR:

- Starting allele frequency: 0.5
- Mutation rate: 0
- Fitness of genotype AA, AB, and BB: 1
- Migration rate: 0
- Number of populations: 10
- Number of generations: 100
	 
This way we reduce the mechanisms (e.g. selection, mutation, migration) that can impact allele frequency changes to genetic drift, and how the latter behaves with different population sizes.
 
## Questions ##
When these starting parameters are all set, answer the following questions.


1. Press `Run Simulation` and describe what you see
   1. What is the on the axes?
   2. What does every line represent?
2. How does this change, if we set the populations size to 1000
3. How does this change, if we set the populations size to 10000
4. Run 20 replicates of the last three runs (population size: 100, 1000, 10000)
   1. Does the mean of the allele frequency (p) change?
   2. Does the variance of the allele frequency (p) change?
5. Are these observations in line with your expectations?
6. Would you expect to observe a similar behavior of the mean and variance of the allele frequency, if we reduce the fitness of genotype AB and BB to 0.9? If not, what would change?
7. What are the underlying mechanisms of these observations?

