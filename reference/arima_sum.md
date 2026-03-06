# Sum ARIMA Models

Sum ARIMA Models

## Usage

``` r
arima_sum(...)
```

## Arguments

- ...:

  list of ARIMA models (created with
  [`arima_model()`](https://rjdverse.github.io/rjd3toolkit/reference/arima_model.md)).

## Value

a `"JD3_ARIMA"` model.

## Details

Adds several Arima models, considering that their innovations are
independent. The sum of two Arima models is computed as follows: the
auto-regressive parts (stationary and non stationary of the aggregated
model are the smaller common multiple of the corresponding polynomials
of the components. The sum of the acf of the modified moving average
polynomials is then computed and factorized, to get the moving average
polynomial and innovation variance of the sum.

## Examples

``` r
mod1 <- arima_model(ar = c(0.1, 0.2), delta = 0, ma = 0)
mod2 <- arima_model(ar = 0, delta = 0, ma = c(0.4))
arima_sum(mod1, mod2)
#> Error in .jcall(obj = "jdplus/toolkit/base/r/arima/ArimaModels", returnSig = "Ljdplus/toolkit/base/core/arima/ArimaModel;",     method = "of", .jarray(as.numeric(model$ar)), .jarray(as.numeric(model$delta)),     .jarray(as.numeric(model$ma)), as.numeric(model$var), FALSE): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/arima/ArimaModels has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
