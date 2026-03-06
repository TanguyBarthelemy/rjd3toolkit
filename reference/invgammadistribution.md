# Inverse-Gamma Distribution

Density, (cumulative) distribution function and random generation for
inverse-gamma distribution.

## Usage

``` r
density_inverse_gamma(shape, scale, x)

cdf_inverse_gamma(shape, scale, x)

random_inverse_gamma(shape, scale, n)
```

## Arguments

- shape, scale:

  shape and scale parameters.

- x:

  vector of quantiles.

- n:

  number of observations.

## Value

numeric vector

The functions density_XXX and cdf_t return numeric vectors of same
length as `x`. The functions random_XXX return random number (numeric
vectors) of length `n`.

## Examples

``` r
density_inverse_gamma(shape = 1, scale = 2, x = 1:10)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "densityInverseGamma",     shape, scale, .jarray(as.numeric(x))): RcallMethod: cannot determine object class
cdf_inverse_gamma(shape = 1, scale = 2, x = 1:10)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "cdfInverseGamma",     shape, scale, .jarray(as.numeric(x))): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
random_inverse_gamma(shape = 1, scale = 2, n = 10)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsInverseGamma",     shape, scale, as.integer(n)): RcallMethod: cannot determine object class
```
