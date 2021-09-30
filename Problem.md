Hw1
================
Yu Si
9/29/2021

\#\#Problem 1

\#\#\#1.1

``` r
set.seed(1234)
#Create the data frame
problem_df = tibble(
  x = rnorm(10),
  vec_logical = c(FALSE, FALSE, TRUE, FALSE,FALSE,TRUE,TRUE,TRUE,FALSE,FALSE),
  vec_char =  character(10),
  vec_factor = factor(c("Level1", "Level2", "Level3","Level1", "Level2", "Level3","Level1", "Level2", "Level3","Level2"))
  )
problem_df
```

    ## # A tibble: 10 × 4
    ##         x vec_logical vec_char vec_factor
    ##     <dbl> <lgl>       <chr>    <fct>     
    ##  1 -1.21  FALSE       ""       Level1    
    ##  2  0.277 FALSE       ""       Level2    
    ##  3  1.08  TRUE        ""       Level3    
    ##  4 -2.35  FALSE       ""       Level1    
    ##  5  0.429 FALSE       ""       Level2    
    ##  6  0.506 TRUE        ""       Level3    
    ##  7 -0.575 TRUE        ""       Level1    
    ##  8 -0.547 TRUE        ""       Level2    
    ##  9 -0.564 FALSE       ""       Level3    
    ## 10 -0.890 FALSE       ""       Level2

``` r
#pull the variable out of data frame
col_1 = pull(problem_df, var=1)
col_2 = pull(problem_df, var=2)
col_3 = pull(problem_df, var=3)
col_4 = pull(problem_df, var=4)
col_1
```

    ##  [1] -1.2070657  0.2774292  1.0844412 -2.3456977  0.4291247  0.5060559
    ##  [7] -0.5747400 -0.5466319 -0.5644520 -0.8900378

``` r
col_2
```

    ##  [1] FALSE FALSE  TRUE FALSE FALSE  TRUE  TRUE  TRUE FALSE FALSE

``` r
col_3
```

    ##  [1] "" "" "" "" "" "" "" "" "" ""

``` r
col_4
```

    ##  [1] Level1 Level2 Level3 Level1 Level2 Level3 Level1 Level2 Level3 Level2
    ## Levels: Level1 Level2 Level3

``` r
#calculate the mean of each variable
mean(col_1)
```

    ## [1] -0.3831574

``` r
mean(col_2)
```

    ## [1] 0.4

``` r
mean(col_3)
```

    ## Warning in mean.default(col_3): argument is not numeric or logical: returning NA

    ## [1] NA

``` r
mean(col_4)
```

    ## Warning in mean.default(col_4): argument is not numeric or logical: returning NA

    ## [1] NA

Based on the results, the numeric and logical variables work and others
don’t work for calculating mean.

\#\#\#1.2

``` r
col_2_numeric = as.numeric(col_2)
col_3_numeric = as.numeric(col_3)
col_4_numeric = as.numeric(col_4)
```

After converting variables from one type to another, I find that the
logical variables become 0 and 1 because of the binary characteristic,
which explains that the mean of this variable is 0.4 because there are
four “1” in 10 numbers. The character what i create is 10 length but it
is all empty. Then using as.numeric, the results are 10 NA. When a
factor is converted into a numeric vector, the numeric codes
corresponding to the factor levels will be returned.

\#\#Problem 2

``` r
data("penguins", package = "palmerpenguins")
summary(penguins)
```

    ##       species          island    bill_length_mm  bill_depth_mm  
    ##  Adelie   :152   Biscoe   :168   Min.   :32.10   Min.   :13.10  
    ##  Chinstrap: 68   Dream    :124   1st Qu.:39.23   1st Qu.:15.60  
    ##  Gentoo   :124   Torgersen: 52   Median :44.45   Median :17.30  
    ##                                  Mean   :43.92   Mean   :17.15  
    ##                                  3rd Qu.:48.50   3rd Qu.:18.70  
    ##                                  Max.   :59.60   Max.   :21.50  
    ##                                  NA's   :2       NA's   :2      
    ##  flipper_length_mm  body_mass_g       sex           year     
    ##  Min.   :172.0     Min.   :2700   female:165   Min.   :2007  
    ##  1st Qu.:190.0     1st Qu.:3550   male  :168   1st Qu.:2007  
    ##  Median :197.0     Median :4050   NA's  : 11   Median :2008  
    ##  Mean   :200.9     Mean   :4202                Mean   :2008  
    ##  3rd Qu.:213.0     3rd Qu.:4750                3rd Qu.:2009  
    ##  Max.   :231.0     Max.   :6300                Max.   :2009  
    ##  NA's   :2         NA's   :2

``` r
nrow(penguins)
```

    ## [1] 344

``` r
ncol(penguins)
```

    ## [1] 8

``` r
flipper_length_mean = mean(penguins$flipper_length_mm, na.rm=TRUE)
```

There 344 observation of 8 variables. The variables are species, island,
bill\_length\_mm, bill\_depth\_mm, flipper\_length\_mm, body\_mass\_g,
sex, year. There are three species: Adelie, Chinstrap and Gentoo. There
are three islands: Biscoe, Dream, Torgersen. The sex variable contain
male and female. The years are 2007, 2008 and 2009. All other variable
are number of specific part. There are 344 rows and 8 columns. The mean
of flipper length is 200.915204678363.
