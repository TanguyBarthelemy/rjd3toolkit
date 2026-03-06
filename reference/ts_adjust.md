# Multiplicative adjustment of a time series for leap year / length of periods

Multiplicative adjustment of a time series for leap year / length of
periods

## Usage

``` r
ts_adjust(s, method = c("LeapYear", "LengthOfPeriod"), reverse = FALSE)
```

## Arguments

- s:

  The original time series

- method:

  `"LeapYear"`: correction for leap year `"LengthOfPeriod"`: correction
  for the length of periods

- reverse:

  Adjustment or reverse operation

## Value

The interpolated series

## Examples

``` r
y <- ABS$X0.2.09.10.M
ts_adjust(y)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsData;",     "of", as.integer(freq), as.integer(start[1]), as.integer(start[2]),     as.double(s)): RcallMethod: cannot determine object class
# with reverse we can find the
all.equal(ts_adjust(ts_adjust(y), reverse = TRUE), y)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsData;",     "of", as.integer(freq), as.integer(start[1]), as.integer(start[2]),     as.double(s)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/timeseries/TsUtility has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
