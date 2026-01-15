# Gamma Distribution

Density, (cumulative) distribution function and random generation for
Gamma distribution.

## Usage

``` r
density_gamma(shape, scale, x)

cdf_gamma(shape, scale, x)

random_gamma(shape, scale, n)
```

## Arguments

- shape, scale:

  shape and scale parameters.

- x:

  vector of quantiles.

- n:

  number of observations.

## Value

numeric vector

## Examples

``` r
density_gamma(shape = 1, scale = 2, x = 1:10)
#>  [1] 0.303265330 0.183939721 0.111565080 0.067667642 0.041042499 0.024893534
#>  [7] 0.015098692 0.009157819 0.005554498 0.003368973
cdf_gamma(shape = 1, scale = 2, x = 1:10)
#>  [1] 0.3934693 0.6321206 0.7768698 0.8646647 0.9179150 0.9502129 0.9698026
#>  [8] 0.9816844 0.9888910 0.9932621
random_gamma(shape = 1, scale = 2, n = 10)
#>  [1] 1.1031746 2.2163572 0.3143508 1.0511797 0.6162765 0.5529671 3.0245214
#>  [8] 1.8585481 2.7932847 0.7282144
```
