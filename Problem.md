Hw1
================
Yu Si
9/29/2021

\#\#Problem 1

\#\#\#1.1

``` r
set.seed(1234)
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
