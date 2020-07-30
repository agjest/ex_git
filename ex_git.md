Git example
================

# Introduction

Just a sentence to check that git works from my virtual PC. I think
it\`s fixed now. Merge conflict opens in RStudio editor also on PC.

## Density plot

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

![](ex_git_files/figure-gfm/xdensity-1.png)<!-- -->

``` r
rm(x)
```

## Points plot

We will be using the `cars` dataset. See `help(cars)` for details about
the two variables.

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

``` r
ggplot(cars, mapping = aes(x = speed, y = dist)) +
  geom_point()
```

![](ex_git_files/figure-gfm/cars-points-plot-1.png)<!-- -->

### Spline

We might want to add a smooth.

``` r
ggplot(cars, mapping = aes(x = speed, y = dist)) +
  geom_point() +
  geom_smooth()
```

![](ex_git_files/figure-gfm/cars-points-plot-smooth-1.png)<!-- -->

### Linear model

We might also want a plain linear model.

``` r
ggplot(cars, mapping = aes(x = speed, y = dist)) +
  geom_point() +
  geom_smooth(method = "lm")
```

![](ex_git_files/figure-gfm/cars-points-plot-smooth-lm-1.png)<!-- -->

``` r
mod <- lm(dist ~ speed, data = cars)
summary(mod)
```

    ## 
    ## Call:
    ## lm(formula = dist ~ speed, data = cars)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -29.069  -9.525  -2.272   9.215  43.201 
    ## 
    ## Coefficients:
    ##             Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept) -17.5791     6.7584  -2.601   0.0123 *  
    ## speed         3.9324     0.4155   9.464 1.49e-12 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 15.38 on 48 degrees of freedom
    ## Multiple R-squared:  0.6511, Adjusted R-squared:  0.6438 
    ## F-statistic: 89.57 on 1 and 48 DF,  p-value: 1.49e-12
