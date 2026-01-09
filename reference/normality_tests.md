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
#> Value: 3.429605 
#> P-Value: 0.1800 
doornikhansen(x)
#> Value: 3.490013 
#> P-Value: 0.1746 
jarquebera(x)
#> Value: 3.661209 
#> P-Value: 0.1603 
skewness(x)
#> Value: 0.4444796 
#> P-Value: 0.0696 
kurtosis(x)
#> Value: 3.181264 
#> P-Value: 0.7114 

x <- random_t(2, 100) # alternative
bowmanshenton(x)
#> Value: 5.662498 
#> P-Value: 0.0589 
doornikhansen(x)
#> Value: 7.72347 
#> P-Value: 0.0210 
jarquebera(x)
#> Value: 6.873352 
#> P-Value: 0.0322 
skewness(x)
#> Value: -0.1449105 
#> P-Value: 0.5541 
kurtosis(x)
#> Value: 4.12916 
#> P-Value: 0.0212 
```
