# Canova-Hansen test for stable trading days

Canova-Hansen test for stable trading days

## Usage

``` r
td_canovahansen(
  s,
  differencing,
  kernel = c("Bartlett", "Square", "Welch", "Tukey", "Hamming", "Parzen"),
  order = NA
)
```

## Arguments

- s:

  a `ts` object that corresponds to the input time series to test.

- differencing:

  Differencing lags.

- kernel:

  Kernel used to compute the robust covariance matrix.

- order:

  The truncation parameter used to compute the robust covariance matrix.

## Value

list with the ftest on td, the joint test and the details for the
stability of the different days (starting with Mondays).

## Examples

``` r
s <- log(ABS$X0.2.20.10.M)
td_canovahansen(s, c(1, 12))
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsData;",     "of", as.integer(freq), as.integer(start[1]), as.integer(start[2]),     as.double(s)): RcallMethod: cannot determine object class
```
