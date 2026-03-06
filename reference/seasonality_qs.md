# QS (seasonal Ljung-Box) test.

QS (seasonal Ljung-Box) test.

## Usage

``` r
seasonality_qs(data, period = NA, nyears = 0, type = 1)
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

- type:

  1 for positive autocorrelations, -1 for negative autocorrelations, 0
  for all autocorrelations. By default (`type = 1`)

## Value

A `c("JD3_TEST", "JD3")` object (see
[`statisticaltest()`](https://rjdverse.github.io/rjd3toolkit/reference/statisticaltest.md)
for details).

## Examples

``` r
s <- do_stationary(log(ABS$X0.2.09.10.M))$ddata
#> Error in .jcall("jdplus/toolkit/base/r/modelling/Differencing", "Ljdplus/toolkit/base/core/modelling/StationaryTransformation;",     "doStationary", as.numeric(data), as.integer(period)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
seasonality_qs(s)
#> Error: object 's' not found
seasonality_qs(random_t(2, 1000), 7)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsT",     df, as.integer(n)): RcallMethod: cannot determine object class
```
