# Promote a R time series to a "full JDemetra+ time series"

Promote a R time series to a "full JDemetra+ time series"

## Usage

``` r
data_to_ts(s, name)
```

## Arguments

- s:

  R time series (class TS)

- name:

  name of the series

## Value

Returns a java object of class JD3_TS

## Examples

``` r
s <- ABS$X0.2.09.10.M
t <- data_to_ts(s, "test")
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsData;",     "of", as.integer(freq), as.integer(start[1]), as.integer(start[2]),     as.double(s)): RcallMethod: cannot determine object class
```
