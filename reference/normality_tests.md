# Normality Tests

Set of functions to test the normality of a time series.

## Usage

``` r
bowmanshenton(data)

doornikhansen(data)

jarquebera(data, k = 0, sample = TRUE)

skewness(data)

kurtosis(data)
```

## Arguments

- data:

  data being tested.

- k:

  number of degrees of freedom to be subtracted if the input time series
  is a series of residuals.

- sample:

  boolean indicating if unbiased empirical moments should be computed.

## Value

A `c("JD3_TEST", "JD3")` object (see
[`statisticaltest`](https://rjdverse.github.io/rjd3toolkit/reference/statisticaltest.md)
for details).

## Functions

- `bowmanshenton()`: Bowman-Shenton test

- `doornikhansen()`: Doornik-Hansen test

- `jarquebera()`: Jarque-Bera test

- `skewness()`: Skewness test

- `kurtosis()`: Kurtosis test

## Examples

``` r
x <- rnorm(100) # null
bowmanshenton(x)
#> Value: 3.511406 
#> P-Value: 0.1728 
doornikhansen(x)
#> Value: 3.544144 
#> P-Value: 0.1700 
jarquebera(x)
#> Value: 3.754974 
#> P-Value: 0.1530 
skewness(x)
#> Value: 0.4484815 
#> P-Value: 0.0671 
kurtosis(x)
#> Value: 3.195435 
#> P-Value: 0.6899 

x <- random_t(2, 100) # alternative
bowmanshenton(x)
#> Value: 12.72727 
#> P-Value: 0.0017 
doornikhansen(x)
#> Value: 9.896099 
#> P-Value: 0.0071 
jarquebera(x)
#> Value: 14.68598 
#> P-Value: 0.0006 
skewness(x)
#> Value: 0.437176 
#> P-Value: 0.0743 
kurtosis(x)
#> Value: 4.513292 
#> P-Value: 0.0020 
```
