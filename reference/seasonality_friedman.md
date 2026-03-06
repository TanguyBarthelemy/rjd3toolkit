# Friedman Seasonality Test

Friedman Seasonality Test

## Usage

``` r
seasonality_friedman(data, period = NA, nyears = 0)
```

## Arguments

- data:

  the input data.

- period:

  Tested periodicity. Can be missing if the input is a time series

- nyears:

  Number of periods or number of cycles considered in the test, at the
  end of the series: in periods (positive value) or years (negative
  values). By default (`nyears = 0`), the entire sample is used.

## Value

A `c("JD3_TEST", "JD3")` object (see
[`statisticaltest()`](https://rjdverse.github.io/rjd3toolkit/reference/statisticaltest.md)
for details).

## Details

Non parametric test ("ANOVA"-type).

## Examples

``` r
s <- do_stationary(log(ABS$X0.2.09.10.M))$ddata
#> Error in .jcall("jdplus/toolkit/base/r/modelling/Differencing", "Ljdplus/toolkit/base/core/modelling/StationaryTransformation;",     "doStationary", as.numeric(data), as.integer(period)): RcallMethod: cannot determine object class
seasonality_friedman(s)
#> Error: object 's' not found
seasonality_friedman(random_t(2, 1000), 12)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsT",     df, as.integer(n)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/modelling/Differencing has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
