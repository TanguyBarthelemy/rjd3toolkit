# Differencing of a series

Differencing of a series

## Usage

``` r
differences(data, lags = 1, mean = TRUE)
```

## Arguments

- data:

  The series to be differenced.

- lags:

  Lags of the differencing.

- mean:

  Apply a mean correction at the end of the differencing process.

## Value

The differenced series.

## Examples

``` r
differences(Retail$BookStores, c(1, 1, 12), FALSE)
#> Error in .jcall("jdplus/toolkit/base/r/modelling/Differencing", "[D",     "differences", as.numeric(data), .jarray(as.integer(lags)),     mean): RcallMethod: cannot determine object class
```
