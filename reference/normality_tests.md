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
#> Value: 0.09858598 
#> P-Value: 0.9519 
doornikhansen(x)
#> Value: 0.05114668 
#> P-Value: 0.9748 
jarquebera(x)
#> Value: 0.04550024 
#> P-Value: 0.9775 
skewness(x)
#> Value: -0.02688914 
#> P-Value: 0.9126 
kurtosis(x)
#> Value: 2.855887 
#> P-Value: 0.7686 

x <- random_t(2, 100) # alternative
bowmanshenton(x)
#> Value: 10.22502 
#> P-Value: 0.0060 
doornikhansen(x)
#> Value: 8.780499 
#> P-Value: 0.0124 
jarquebera(x)
#> Value: 11.87629 
#> P-Value: 0.0026 
skewness(x)
#> Value: 0.3934294 
#> P-Value: 0.1082 
kurtosis(x)
#> Value: 4.354569 
#> P-Value: 0.0057 
```
