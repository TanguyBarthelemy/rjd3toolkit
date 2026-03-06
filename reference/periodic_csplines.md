# Periodic cardinal cubic splines

Periodic cardinal cubic splines

## Usage

``` r
periodic_csplines(x, pos)
```

## Arguments

- x:

  Abscissas of the knots

- pos:

  Requested positions

## Value

A matrix (len(pos) x len(knots))

## Examples

``` r
s<-periodic_csplines(x = c(0,.2,.3, .9,.95, 1), pos=seq(0,1,0.01))
#> Error in .jcall("jdplus/toolkit/base/r/math/CubicSplines", "Ljdplus/toolkit/base/api/math/matrices/Matrix;",     "periodicCardinalSplines", .jarray(as.numeric(x)), .jarray(as.numeric(pos))): RcallMethod: cannot determine object class
matplot(s, type='l')
#> Error: object 's' not found
```
