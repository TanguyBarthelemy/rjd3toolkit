# Inverse-Gaussian Distribution

Density, (cumulative) distribution function and random generation for
inverse-gaussian distribution.

## Usage

``` r
density_inverse_gaussian(shape, scale, x)

cdf_inverse_gaussian(shape, scale, x)

random_inverse_gaussian(shape, scale, n)
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

The functions density_XXX and cdf_t return numeric vectors of same
length as `x`. The functions random_XXX return random number (numeric
vectors) of length `n`.

## Examples

``` r
density_inverse_gaussian(shape = 1, scale = 2, x = 1:10)
#>  [1] 5.641896e-01 1.209854e-01 2.862094e-02 7.433143e-03 2.056969e-03
#>  [6] 5.951656e-04 1.779359e-04 5.454267e-05 1.705081e-05 5.415515e-06
random_inverse_gaussian(shape = 1, scale = 2, n = 10)
#>  [1] 2.2694316 0.3654894 4.4802699 1.3752811 1.7301353 0.8944295 1.0111699
#>  [8] 0.5955668 1.0599734 1.7589364
```
