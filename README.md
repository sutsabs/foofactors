
<!-- README.md is generated from README.Rmd. Please edit that file -->

foofactors
==========

<!-- badges: start -->
<!-- badges: end -->

Factors are a very useful type of variable in R, but they can also be
very aggravating. This package provides some helper functions for the
care and feeding of factors.

Installation
------------

You can install the released version of foofactors from
[CRAN](https://CRAN.R-project.org) with:

``` r
devtools::install_github("jennybc/foofactors")
```

Example
-------

Binding two factors via `fbind()`:

``` r
library(foofactors)
a <- factor(c("character", "hits", "your", "eyeballs"))
b <- factor(c("but", "integer", "where it", "counts"))
```

Simply catenating two factors leads to a result that most don’t expect.

``` r
c(a, b)
#> [1] 1 3 4 2 1 3 4 2
```

The `fbind()` function glues two factors together and returns factor.

``` r
fbind(a, b)
#> [1] character hits      your      eyeballs  but       integer   where it 
#> [8] counts   
#> Levels: but character counts eyeballs hits integer where it your
```

Often we want a table of frequencies for the levels of a factor. The
base `table()` function returns an object of class `table`, which can be
inconvenient for downstream work.

``` r
set.seed(1234)
x <- factor(sample(letters[1:5], size = 100, replace = TRUE))
table(x)
#> x
#>  a  b  c  d  e 
#> 19 19 21 22 19
```

Often we want a table of frequencies for the levels of a factor. The
base `table()` function returns an object of class `table`, which can be
inconvenient for downstream work.

``` r
set.seed(1234)
x <- factor(sample(letters[1:5], size = 100, replace = TRUE))
table(x)
#> x
#>  a  b  c  d  e 
#> 19 19 21 22 19
```
