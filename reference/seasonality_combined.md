# "X12" Test On Seasonality

"X12" Test On Seasonality

## Usage

``` r
seasonality_combined(
  data,
  period = NA,
  firstperiod = cycle(data)[1],
  mul = TRUE
)
```

## Arguments

- data:

  the input data.

- period:

  Tested periodicity. Can be missing if the input is a time series

- firstperiod:

  Position in a cycle of the first obs. For example, for a monthly,
  `firstperiod = 1` means January. If `data` is not a `"ts"` object,
  `firstperiod = 1` by default.

- mul:

  boolean indicating if the seasonal decomposition is multiplicative
  (`mul = TRUE`) or additive (`mul = FALSE`).

## Value

a `list` with several seasonnality tests (kruskalwallis, stable and
evolutive)

## Details

Combined test on the presence of identifiable seasonality (see Ladiray
and Quenneville, 1999).

## Examples

``` r
s <- do_stationary(log(ABS$X0.2.09.10.M))$ddata
#> Error in .jcall("jdplus/toolkit/base/r/modelling/Differencing", "Ljdplus/toolkit/base/core/modelling/StationaryTransformation;",     "doStationary", as.numeric(data), as.integer(period)): RcallMethod: cannot determine object class
seasonality_combined(s)
#> Error: object 's' not found
seasonality_combined(random_t(2, 1000), 7)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsT",     df, as.integer(n)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/modelling/Differencing has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
