# Natural cubic spline

Natural cubic spline

## Usage

``` r
natural_cspline(x, y, pos)
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
s<-natural_cspline(x = c(0,.2,.3, .9,.95), y= c(1,3,5,8,12), pos=seq(0,1,0.01))
#> Error in .jcall("jdplus/toolkit/base/r/math/CubicSplines", "[D", "natural",     .jarray(as.numeric(x)), .jarray(as.numeric(y)), .jarray(as.numeric(pos))): RcallMethod: cannot determine object class
plot(s, type='l')
#> Error: object 's' not found
```
