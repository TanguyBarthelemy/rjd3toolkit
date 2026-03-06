# Student Distribution

Probability Density Function (PDF), Cumulative Density Function (CDF)
and generation of random variables following a Student distribution.

## Usage

``` r
density_t(df, x)

cdf_t(df, x)

random_t(df, n)
```

## Arguments

- df:

  degrees of freedom.

- x:

  vector of quantiles.

- n:

  number of observations.

## Value

The functions density_XXX and cdf_t return numeric vectors of same
length as `x`. The functions random_XXX return random number (numeric
vectors) of length `n`.

## Examples

``` r
# Probability density function of T with 2 degrees of freedom.
z <- density_t(df = 2, .01 * seq(-100, 100, 1))
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "densityT",     df, .jarray(as.numeric(x))): RcallMethod: cannot determine object class
# Generating a random vector with each component drawn from a T(2) distribution
z <- random_t(2, 100)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsT",     df, as.integer(n)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
# Computing the probabilty that the random variable X following a T distribution
# with df degrees of freedom is lower than x
z <- cdf_t(df = 12, x = 1.2)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "cdfT",     df, .jarray(as.numeric(x))): RcallMethod: cannot determine object class
z
#> Error: object 'z' not found
z <- cdf_t(df = 12, x = c(0:10)) # array of values
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "cdfT",     df, .jarray(as.numeric(x))): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
z
#> Error: object 'z' not found
```
