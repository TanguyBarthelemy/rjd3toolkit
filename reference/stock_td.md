# Trading day Regressor for Stock series

Allows to generate a specific regressor for correcting trading days
effects in Stock series.

## Usage

``` r
stock_td(frequency, start, length, s, w = 31)
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

- w:

  indicates day of the month when inventories and other stocks are
  reported. (to denote the last day of the month enter 31).

## Value

Time series (object of class `c("ts","mts","matrix")`).

## Details

The regressor will have the value -1 if the w-th day is a Sunday, 1 if
it is a Monday as 0 otherwise.

## References

More information on calendar correction in JDemetra+ online
documentation:
<https://jdemetra-new-documentation.netlify.app/a-calendar-correction>

## See also

[`calendar_td`](https://rjdverse.github.io/rjd3toolkit/reference/calendar_td.md)

## Examples

``` r
stock_td(frequency = 12L, start = c(1990L, 1L), length = 480L, w = 1L)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Distributions has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
