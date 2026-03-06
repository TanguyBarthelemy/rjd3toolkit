# B-Splines

B-Splines

## Usage

``` r
bsplines(order = 4, knots, pos)
```

## Arguments

- order:

  Order of the splines (4 for cubic)

- knots:

  Knots of the splines (in \[0, period\[)

- pos:

  Requested positions (in \[0, period\[). The rows of the returned
  matrix will correspond to those positions

## Value

A matrix (len(pos) x len(knots))

## Examples

``` r
s<-bsplines(knots = c(0,.2,.3, .9,.95, 1), pos=seq(0,1,0.01))
#> Error in .jcall("jdplus/toolkit/base/r/math/BSplines", "Ljdplus/toolkit/base/api/math/matrices/Matrix;",     "of", as.integer(order), .jarray(as.numeric(knots)), .jarray(as.numeric(pos))): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Tests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
matplot(s, type='l')
#> Error: object 's' not found
```
