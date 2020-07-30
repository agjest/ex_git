Git example
================

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

![](ex_git_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

``` r
rm(x)
```
