# Autocorrelation Functions

Autocorrelation Functions

## Usage

``` r
autocorrelations(data, mean = TRUE, n = 15)

autocorrelations_partial(data, mean = TRUE, n = 15)

autocorrelations_inverse(data, nar = 30, n = 15)
```

## Arguments

- data:

  data being tested.

- mean:

  Mean correction. If `TRUE`, the auto-correlations are computed as
  usual. If `FALSE`, we consider that the (known) mean is 0 and that the
  series has been corrected for it.

- n:

  maximum lag at which to calculate the stats.

- nar:

  number of AR lags used to compute inverse autocorrelations.

## Value

`autocorrelations()` returns a vector of length `n` with the
autocorrelations. `autocorrelations_partial()` returns a vector of
length `n` with the partial autocorrelations.
`autocorrelations_inverse()` returns a vector of length `n` with the
inverse autocorrelations.

## Examples

``` r
x <- ABS$X0.2.09.10.M
autocorrelations(x)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "[D", "autocorrelations",     as.numeric(data), as.logical(mean), as.integer(n)): RcallMethod: cannot determine object class
autocorrelations_partial(x)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "[D", "partialAutocorrelations",     as.numeric(data), as.logical(mean), as.integer(n)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Tests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
autocorrelations_inverse(x)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "[D", "inverseAutocorrelations",     as.numeric(data), as.integer(nar), as.integer(n)): RcallMethod: cannot determine object class
```
