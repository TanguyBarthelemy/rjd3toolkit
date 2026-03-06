# Leap Year regressor

Allows to generate a regressor correcting for the leap year or
length-of-period effect.

## Usage

``` r
lp_variable(
  frequency,
  start,
  length,
  s,
  type = c("LeapYear", "LengthOfPeriod")
)
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

- type:

  the modelling of the leap year effect: as a contrast variable
  (`type = "LeapYear"`, default) or by a length-of-month (or
  length-of-quarter; `type = "LengthOfPeriod"`).

## Value

Time series (object of class `"ts"`)

## References

More information on calendar correction in JDemetra+ online
documentation:
<https://jdemetra-new-documentation.netlify.app/a-calendar-correction>

## See also

[`calendar_td`](https://rjdverse.github.io/rjd3toolkit/reference/calendar_td.md)

## Examples

``` r
# Leap years occur in year 2000, 2004, 2008 and 2012
lp_variable(4, start = c(2000, 1), length = 4 * 13)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): RcallMethod: cannot determine object class
lper <- lp_variable(12, c(2000, 1), length = 10 * 12, type = "LengthOfPeriod")
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/timeseries/TsUtility has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
