# Runs Tests around the mean or the median

Functions to compute runs test around the mean or the median
(`testofruns`) or up and down runs test (`testofupdownruns`) to check
randomness of a data.

## Usage

``` r
testofruns(data, mean = TRUE, number = TRUE)

testofupdownruns(data, number = TRUE)
```

## Arguments

- data:

  data being tested.

- mean:

  If `TRUE`, runs around the mean. Otherwise, runs around the median.

- number:

  If `TRUE`, test the number of runs. Otherwise, test the lengths of the
  runs.

## Value

A `c("JD3_TEST", "JD3")` object (see
[`statisticaltest()`](https://rjdverse.github.io/rjd3toolkit/reference/statisticaltest.md)
for details).

## Functions

- `testofruns()`: Runs test around mean or median

- `testofupdownruns()`: up and down runs test

## Examples

``` r
x <- random_t(5, 1000)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsT",     df, as.integer(n)): RcallMethod: cannot determine object class
# random values
testofruns(x)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "testOfRuns", as.numeric(data), as.logical(mean), as.logical(number)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
testofupdownruns(x)
#> Error: object 'x' not found
# non-random values
testofruns(ABS$X0.2.09.10.M)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "testOfRuns", as.numeric(data), as.logical(mean), as.logical(number)): RcallMethod: cannot determine object class
testofupdownruns(ABS$X0.2.09.10.M)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "testOfUpDownRuns", as.numeric(data), as.logical(number)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Tests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
