# Periodic B-Splines

Periodic B-Splines

## Usage

``` r
periodic_bsplines(order = 4, period = 1, knots, pos)
```

## Arguments

- order:

  Order of the splines (4 for cubic)

- period:

  Period of the splines (1 by default)

- knots:

  Knots of the splines (in \[0, period\[)

- pos:

  Requested positions (in \[0, period\[). The rows of the returned
  matrix will correspond to those positions

## Value

A matrix (len(pos) x len(knots))

## Examples

``` r
s<-periodic_bsplines(knots = c(0,.2,.3, .9,.95), pos=seq(0,1,0.01))
#> Error in .jcall("jdplus/toolkit/base/r/math/BSplines", "Ljdplus/toolkit/base/api/math/matrices/Matrix;",     "periodic", as.integer(order), as.numeric(period), .jarray(as.numeric(knots)),     .jarray(as.numeric(pos))): RcallMethod: cannot determine object class
matplot(s, type='l')
#> Error: object 's' not found
```
