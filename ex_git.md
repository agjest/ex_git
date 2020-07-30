Git example
================

``` r
library(tidyverse)
```

    ## -- Attaching packages --------------------- tidyverse 1.3.0 --

    ## v ggplot2 3.3.2     v purrr   0.3.4
    ## v tibble  3.0.3     v dplyr   1.0.0
    ## v tidyr   1.1.0     v stringr 1.4.0
    ## v readr   1.3.1     v forcats 0.5.0

    ## -- Conflicts ------------------------ tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

# Introduction

Just a sentence to check that git works from my virtual PC. I think
it\`s fixed now. Merge conflict opens in RStudio editor also on PC.

``` r
set.seed(5566)
x <- data.frame(x=rnorm(1000000, mean = 2, sd = 1))
mean(x$x); sd(x$x)
```

    ## [1] 2.001167

    ## [1] 0.999934

``` r
ggplot(x, aes(x)) +
  geom_density()
```

![](ex_git_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

``` r
rm(x)
```
