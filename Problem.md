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
