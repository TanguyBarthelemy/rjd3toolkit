# Interpolation of a time series with missing values

Interpolation of a time series with missing values

## Usage

``` r
ts_interpolate(s, method = c("airline", "average"))
```

## Arguments

- s:

  time series with missing values

- method:

  airline: interpolation through an estimated airline model (Default)
  average: interpolation using the average of the previous and next non
  missing values

## Value

The interpolated series

## Examples

``` r
y<- rjd3toolkit::ABS$X0.2.09.10.M
y[400:410]<-NA
y1<-ts_interpolate(y)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsData;",     "of", as.integer(freq), as.integer(start[1]), as.integer(start[2]),     as.double(s)): RcallMethod: cannot determine object class
y1[390:420]
#> Error: object 'y1' not found
```
