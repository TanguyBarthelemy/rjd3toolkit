# Makes a UCARIMA model canonical

More specifically, put all the noise of the components in one dedicated
component

## Usage

``` r
ucarima_canonical(ucm, cmp = 0, adjust = TRUE)
```

## Arguments

- ucm:

  An UCARIMA model returned by
  [`ucarima_model()`](https://rjdverse.github.io/rjd3toolkit/reference/ucarima_model.md).

- cmp:

  Index of the component that will contain the noises; 0 if a new
  component with all the noises will be added to the model

- adjust:

  If TRUE, some noise could be added to the model to ensure that all the
  components has positive (pseudo-)spectrum

## Value

A new UCARIMA model

## Examples

``` r
mod1 <- arima_model("trend", delta = c(1, -2, 1))
mod2 <- arima_model("noise", variance = 1600)
hp <- ucarima_model(components = list(mod1, mod2))
#> Error in .jcall(obj = "jdplus/toolkit/base/r/arima/ArimaModels", returnSig = "Ljdplus/toolkit/base/core/arima/ArimaModel;",     method = "of", .jarray(as.numeric(model$ar)), .jarray(as.numeric(model$delta)),     .jarray(as.numeric(model$ma)), as.numeric(model$var), FALSE): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/timeseries/TsDataCollector has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
hpc <- ucarima_canonical(hp, cmp = 2)
#> Error: object 'hp' not found
```
