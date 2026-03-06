# Creates an UCARIMA model, which is composed of ARIMA models with independent innovations.

Creates an UCARIMA model, which is composed of ARIMA models with
independent innovations.

## Usage

``` r
ucarima_model(model = NULL, components, complements = NULL, checkmodel = FALSE)
```

## Arguments

- model:

  The reduced model. Usually not provided.

- components:

  The ARIMA models representing the components

- complements:

  Complements of (some) components. Usually not provided

- checkmodel:

  When the model is provided and *checkmodel* is TRUE, we check that it
  indeed corresponds to the reduced form of the components; similar
  controls are applied on complements. Currently not implemented

## Value

A list with the reduced model, the components and their complements

## Examples

``` r
mod1 <- arima_model("trend", delta = c(1, -2, 1))
mod2 <- arima_model("noise", variance = 1600)
hp <- ucarima_model(components = list(mod1, mod2))
#> Error in .jcall(obj = "jdplus/toolkit/base/r/arima/ArimaModels", returnSig = "Ljdplus/toolkit/base/core/arima/ArimaModel;",     method = "of", .jarray(as.numeric(model$ar)), .jarray(as.numeric(model$delta)),     .jarray(as.numeric(model$ma)), as.numeric(model$var), FALSE): RcallMethod: cannot determine object class
print(hp$model)
#> Error: object 'hp' not found
```
