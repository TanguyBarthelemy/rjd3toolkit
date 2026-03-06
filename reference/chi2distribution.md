# Chi-Squared Distribution

Density, (cumulative) distribution function and random generation for
chi-squared distribution.

## Usage

``` r
density_chi2(df, x)

cdf_chi2(df, x)

random_chi2(df, n)
```

## Arguments

- df:

  degrees of freedom.

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
density_chi2(df = 3, 1:10)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "densityChi2",     df, .jarray(as.numeric(x))): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/timeseries/TsUtility has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
cdf_chi2(df = 3, 1:10)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "cdfChi2",     df, .jarray(as.numeric(x))): RcallMethod: cannot determine object class
random_chi2(df = 3, n = 10)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsChi2",     df, as.integer(n)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
