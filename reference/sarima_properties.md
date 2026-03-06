# SARIMA Properties

SARIMA Properties

## Usage

``` r
sarima_properties(model, nspectrum = 601, nacf = 36)
```

## Arguments

- model:

  a `"JD3_SARIMA"` model (created with
  [`sarima_model()`](https://rjdverse.github.io/rjd3toolkit/reference/sarima_model.md)).

- nspectrum:

  number of points in \[0, pi\] to calculate the spectrum.

- nacf:

  maximum lag at which to calculate the acf.

## Value

List with the acf and the spectrum of the model.

## Examples

``` r
mod1 <- sarima_model(period = 12, d = 1, bd = 1, theta = 0.2, btheta = 0.2)
sarima_properties(mod1)
#> Error in .jcall("jdplus/toolkit/base/r/arima/SarimaModels", "Ljdplus/toolkit/base/core/sarima/SarimaModel;",     "of", as.integer(model$period), .jarray(as.numeric(model$phi)),     as.integer(model$d), .jarray(as.numeric(model$theta)), .jarray(as.numeric(model$bphi)),     as.integer(model$bd), .jarray(as.numeric(model$btheta))): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/arima/SarimaModels has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
