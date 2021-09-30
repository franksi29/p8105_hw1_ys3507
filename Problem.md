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
```
