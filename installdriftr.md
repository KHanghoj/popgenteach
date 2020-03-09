Open `R` or `Rstudio` on your local machine an copy the following code:

```R
ipak <- function(pkg){
    new.pkg <- pkg[!(pkg %in% installed.packages()[, "Package"])]
    if (length(new.pkg)){
        install.packages(new.pkg, dependencies = TRUE)
    }
    sapply(pkg, require, character.only = TRUE)
}
ipak(c("shiny", "viridis", "reshape", "ggplot2", "plyr", "magrittr"))
```
