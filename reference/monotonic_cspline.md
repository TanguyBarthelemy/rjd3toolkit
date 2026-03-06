# Monotonic cubic spline

Monotonic cubic spline

## Usage

``` r
monotonic_cspline(x, y, pos)
```

## Arguments

- x:

  Abscissas of the knots

- y:

  Ordinates of the knots

- pos:

  Requested positions

## Value

An array corresponding to the values of the spline at the requested
positions

## Examples

``` r
s<-monotonic_cspline(x = c(0,.2,.3, .9,.95), y= c(1,3,5,8,12), pos=seq(0,1,0.01))
#> Error in .jcall("jdplus/toolkit/base/r/math/CubicSplines", "[D", "monotonic",     .jarray(as.numeric(x)), .jarray(as.numeric(y)), .jarray(as.numeric(pos))): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/timeseries/TsUtility has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
plot(s, type='l')
#> Error: object 's' not found
```
