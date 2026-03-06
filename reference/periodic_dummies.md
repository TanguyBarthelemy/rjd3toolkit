# Periodic dummies and contrasts

Periodic dummies and contrasts

## Usage

``` r
periodic_dummies(frequency, start, length, s)

periodic_contrasts(frequency, start, length, s)
```

## Arguments

- frequency:

  Frequency of the series, number of periods per year (12, 4, 3, 2...)

- start, length:

  First date (array with the first year and the first period, for
  instance `c(1980, 1)`) and number of periods of the output variables.
  Can also be provided with the `s` argument

- s:

  time series used to get the dates for the trading days variables. If
  supplied the parameters `frequency`, `start` and `length` are ignored.

## Value

a `mts` object with `frequency` column

## Details

The function `periodic_dummies()` creates as many time series as types
of periods in a year (4 or 12) with the value one only for one given
type of period (ex Q1) The `periodic_contrasts()` function is based on
periodic_dummies but adds -1 to the period preceding a 1.

## Examples

``` r
# periodic dummies for a quarterly series
p <- periodic_dummies(4, c(2000, 1), 60)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/math/CubicSplines has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
# periodic contrasts for a quarterly series
q <- periodic_contrasts(4, c(2000, 1), 60)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): RcallMethod: cannot determine object class
q[1:9, ]
#> Error in q[1:9, ]: object of type 'closure' is not subsettable
```
