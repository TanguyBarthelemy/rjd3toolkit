# Properties of an ARIMA model

The (pseudo-)spectrum and the auto-covariances of the model are returned

## Usage

``` r
arima_properties(model, nspectrum = 601, nac = 36)
```

## Arguments

- model:

  a `"JD3_ARIMA"` model (created with
  [`arima_model()`](https://rjdverse.github.io/rjd3toolkit/reference/arima_model.md)).

- nspectrum:

  number of points to calculate the spectrum; th points are uniformly
  distributed in \[0, pi\]

- nac:

  maximum lag at which to calculate the auto-covariances; if the model
  is non-stationary, the auto-covariances are computed on its stationary
  transformation.

## Value

A list with the auto-covariances and with the (pseudo-)spectrum

## Examples

``` r
mod1 <- arima_model(ar = c(0.1, 0.2), delta = c(1, -1), ma = 0)
arima_properties(mod1)
#> Error in .jcall(obj = "jdplus/toolkit/base/r/arima/ArimaModels", returnSig = "Ljdplus/toolkit/base/core/arima/ArimaModel;",     method = "of", .jarray(as.numeric(model$ar)), .jarray(as.numeric(model$delta)),     .jarray(as.numeric(model$ma)), as.numeric(model$var), FALSE): RcallMethod: cannot determine object class
```
