# Aggregation of time series

Makes a frequency change of this series.

## Usage

``` r
aggregate(
  s,
  nfreq = 1,
  conversion = c("Sum", "Average", "First", "Last", "Min", "Max"),
  complete = TRUE
)
```

## Arguments

- s:

  the input time series.

- nfreq:

  the new frequency. Must be la divisor of the frequency of `s`.

- conversion:

  Aggregation mode: sum (`"Sum"`), average (`"Average"`), first
  observation (`"First"`), last observation (`"Last"`), minimum
  (`"Min"`), maximum (`"Max"`).

- complete:

  Boolean indicating if the observation for a given period in the new
  series is set missing if some data in the original series are missing.

## Value

A new time series of frequency `nfreq`.

## Examples

``` r
s <- ABS$X0.2.09.10.M
# Annual sum
aggregate(s, nfreq = 1, conversion = "Sum") # first and last years removed
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsData;",     "of", as.integer(freq), as.integer(start[1]), as.integer(start[2]),     as.double(s)): RcallMethod: cannot determine object class
aggregate(s, nfreq = 1, conversion = "Sum", complete = FALSE)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsData;",     "of", as.integer(freq), as.integer(start[1]), as.integer(start[2]),     as.double(s)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/timeseries/TsUtility has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
# Quarterly mean
aggregate(s, nfreq = 4, conversion = "Average")
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsData;",     "of", as.integer(freq), as.integer(start[1]), as.integer(start[2]),     as.double(s)): RcallMethod: cannot determine object class
```
