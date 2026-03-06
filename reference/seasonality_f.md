# F-test on seasonal dummies

F-test on seasonal dummies

## Usage

``` r
seasonality_f(data, period = NA, model = c("AR", "D1", "WN"), nyears = 0)
```

## Arguments

- data:

  the input data.

- period:

  Tested periodicity. Can be missing if the input is a time series

- model:

  the model to use for the residuals.

- nyears:

  Number of periods or number of cycles considered in the test, at the
  end of the series: in periods (positive value) or years (negative
  values). By default (`nyears = 0`), the entire sample is used.

## Value

A `c("JD3_TEST", "JD3")` object (see
[`statisticaltest()`](https://rjdverse.github.io/rjd3toolkit/reference/statisticaltest.md)
for details).

## Details

Estimation of a model with seasonal dummies. Joint F-test on the
coefficients of the dummies.

## Examples

``` r
seasonality_f(ABS$X0.2.09.10.M, model = "D1")
#> Error in .jcall("jdplus/sa/base/r/SeasonalityTests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "fTest", as.numeric(data), as.integer(period), model, as.integer(nyears)): RcallMethod: cannot determine object class
seasonality_f(random_t(2, 1000), 7)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsT",     df, as.integer(n)): java.lang.UnsupportedClassVersionError: jdplus/sa/base/r/SeasonalityTests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
