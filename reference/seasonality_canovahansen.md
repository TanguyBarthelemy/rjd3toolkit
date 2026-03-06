# Canova-Hansen seasonality test

Canova-Hansen seasonality test

## Usage

``` r
seasonality_canovahansen(
  data,
  period,
  type = c("Contrast", "Dummy", "Trigonometric"),
  lag1 = TRUE,
  kernel = c("Bartlett", "Square", "Welch", "Tukey", "Hamming", "Parzen"),
  order = NA,
  start = 1
)
```

## Arguments

- data:

  the input data.

- period:

  Tested periodicity. Can be missing if the input is a time series

- type:

  Trigonometric variables, seasonal dummies or seasonal contrasts.

- lag1:

  Lagged variable in the regression model.

- kernel:

  Kernel used to compute the robust Newey-West covariance matrix.

- order:

  The truncation parameter used to compute the robust Newey-West
  covariance matrix.

- start:

  Position of the first observation of the series

## Value

list with the FTest on seasonal variables, the joint test and the
details for the stability of the different seasonal variables

## Examples

``` r
s <- log(ABS$X0.2.20.10.M)
seasonality_canovahansen(s, 12, type = "Contrast")
#> Error in .jcall("jdplus/sa/base/r/SeasonalityTests", "[D", "canovaHansen",     as.numeric(data), as.integer(period), type, as.logical(lag1),     kernel, as.integer(order), as.integer(start - 1)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/arima/SarimaModels has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
seasonality_canovahansen(s, 12, type = "Trigonometric")
#> Error in .jcall("jdplus/sa/base/r/SeasonalityTests", "[D", "canovaHansen",     as.numeric(data), as.integer(period), type, as.logical(lag1),     kernel, as.integer(order), as.integer(start - 1)): RcallMethod: cannot determine object class
```
