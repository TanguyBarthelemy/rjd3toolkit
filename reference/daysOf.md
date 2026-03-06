# Provides a list of dates corresponding to each period of the given time series

Provides a list of dates corresponding to each period of the given time
series

## Usage

``` r
daysOf(ts, pos = 1)
```

## Arguments

- ts:

  A time series

- pos:

  The position of the first considered period.

## Value

A list of the starting dates of each period

## Examples

``` r
daysOf(Retail$BookStores)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/timeseries/TsUtility has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
