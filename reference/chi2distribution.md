# The Chi-Squared Distribution

Density, (cumulative) distribution function and random generation for
chi-squared distribution.

## Usage

``` r
density_chi2(df, x)

cdf_chi2(df, x)

random_chi2(df, n)
```

## Arguments

- df:

  degrees of freedom.

- x:

  vector of quantiles.

- n:

  number of observations.

## Examples

``` r
density_chi2(df = 3, 1:10)
#>  [1] 0.241970725 0.207553749 0.154180330 0.107981933 0.073224913 0.048652173
#>  [7] 0.031873400 0.020666985 0.013295545 0.008500367
cdf_chi2(df = 3, 1:10)
#>  [1] 0.1987480 0.4275933 0.6083748 0.7385359 0.8282029 0.8883898 0.9281022
#>  [8] 0.9539883 0.9707091 0.9814339
random_chi2(df = 3, n = 10)
#>  [1] 1.6471861 2.7324709 7.6341335 1.5634355 0.2252202 4.3015960 2.3529450
#>  [8] 3.1316441 2.1173773 2.2279779
```
