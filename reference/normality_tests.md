# Normality Tests

Set of functions to test the normality of a time series.

## Usage

``` r
bowmanshenton(data)

doornikhansen(data)

jarquebera(data, k = 0, sample = TRUE)

skewness(data)

kurtosis(data)
```

## Arguments

- data:

  data being tested.

- k:

  number of degrees of freedom to be subtracted if the input time series
  is a series of residuals.

- sample:

  boolean indicating if unbiased empirical moments should be computed.

## Value

A `c("JD3_TEST", "JD3")` object (see
[`statisticaltest`](https://rjdverse.github.io/rjd3toolkit/reference/statisticaltest.md)
for details).

## Functions

- `bowmanshenton()`: Bowman-Shenton test

- `doornikhansen()`: Doornik-Hansen test

- `jarquebera()`: Jarque-Bera test

- `skewness()`: Skewness test

- `kurtosis()`: Kurtosis test

## Examples

``` r
x <- rnorm(100) # null
bowmanshenton(x)
#> Error in .jcall(obj = "jdplus/toolkit/base/r/stats/Tests", returnSig = "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     method = "bowmanShenton", as.numeric(data)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/math/CubicSplines has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
doornikhansen(x)
#> Error in .jcall(obj = "jdplus/toolkit/base/r/stats/Tests", returnSig = "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     method = "doornikHansen", as.numeric(data)): RcallMethod: cannot determine object class
jarquebera(x)
#> Error in .jcall(obj = "jdplus/toolkit/base/r/stats/Tests", returnSig = "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     method = "jarqueBera", as.numeric(data), as.integer(k), as.logical(sample)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Tests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
skewness(x)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "skewness", as.numeric(data)): RcallMethod: cannot determine object class
kurtosis(x)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "kurtosis", as.numeric(data)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Tests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0

x <- random_t(2, 100) # alternative
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "randomsT",     df, as.integer(n)): RcallMethod: cannot determine object class
bowmanshenton(x)
#> Error in .jcall(obj = "jdplus/toolkit/base/r/stats/Tests", returnSig = "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     method = "bowmanShenton", as.numeric(data)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
doornikhansen(x)
#> Error in .jcall(obj = "jdplus/toolkit/base/r/stats/Tests", returnSig = "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     method = "doornikHansen", as.numeric(data)): RcallMethod: cannot determine object class
jarquebera(x)
#> Error in .jcall(obj = "jdplus/toolkit/base/r/stats/Tests", returnSig = "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     method = "jarqueBera", as.numeric(data), as.integer(k), as.logical(sample)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Tests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
skewness(x)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "skewness", as.numeric(data)): RcallMethod: cannot determine object class
kurtosis(x)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Tests", "Ljdplus/toolkit/base/api/stats/StatisticalTest;",     "kurtosis", as.numeric(data)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Tests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
