# Exercise 1 #

## Install driftr locally ##

Run the following command to download driftR to your local machine. 
`git clone https://github.com/cjbattey/driftR.git`

Open R and run the following code:

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

This will open your favorite browser with driftR running locally. 


### Alternative availability (on the student server) ###
MISSING

## driftR ##
In this exercise, we will explore the effect of genetic drift on allele frequencies using simulations.
### Starting parameters ###
This software has a series of parameters to tune. Set the following parameters:
     - Starting allele frequency: 0.5
     - Mutation rate: 0
     - Fitness of genotype AA, AB, and BB: 1
     - Migration rate: 0
     - Number of populations: 10
     - Number of generations: 100
	 
This way we reduce the possible mechanisms (selection, mutation, migration) that can impact allele frequency changes to solely genetic drift, and how this behaves with chaning population sizes.

 
## Questions ##
    - Press 'Run Simulation' and describe what you see. What is the on the axis and what does every line show?
    - What happens if we set the populations size to 1000
    - What happens if we set the populations size to 10000
    - Run 20 replicates of the last three runs (population size: 100, 1000, 10000)
      - Does the mean allele frequency (p) change?
      - Does the variance allele frequency (p) change?
    - Are these observations in line with your expectations?
    - Would you expect to observe a similar behavior of the mean and variance of the allele frequency if we reduce the fitness of genotype AB and BB to 0.9? If not, what would change?
    - What are the underlying mechanisms of these observations?

