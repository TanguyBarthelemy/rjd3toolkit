# Ljung-Box Test

Compute Ljung-Box test to check the independence of a data.

## Usage

``` r
ljungbox(data, k = 1, lag = 1, nhp = 0, sign = 0, mean = TRUE)
```

## Arguments

- data:

  data being tested.

- k:

  number of auto-correlations used in the test

- lag:

  number of lags used between two auto-correlations.

- nhp:

  number of hyper parameters (to correct the degree of freedom)

- sign:

  if `sign = 1`, only positive auto-correlations are considered in the
  test. If `sign = -1`, only negative auto-correlations are considered.
  If `sign = 0`, all auto-correlations are integrated in the test.

- mean:

  Mean correction. If `TRUE`, the auto-correlations are computed as
  usual. If `FALSE`, we consider that the (known) mean is 0 and that the
  series has been corrected for it.

## Value

A `c("JD3_TEST", "JD3")` object (see
[`statisticaltest()`](https://rjdverse.github.io/rjd3toolkit/reference/statisticaltest.md)
for details).

## Examples

``` r
ljungbox(random_t(2, 100), lag = 24, k = 1)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "ljungBox", as.numeric(data), as.integer(k), as.integer(lag),     as.integer(nhp), as.integer(sign), as.logical(mean)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
ljungbox(ABS$X0.2.09.10.M, lag = 24, k = 1)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "ljungBox", as.numeric(data), as.integer(k), as.integer(lag),     as.integer(nhp), as.integer(sign), as.logical(mean)): RcallMethod: cannot determine object class
```
