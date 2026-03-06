# Generating trigonometric variables

Generates trigonometric variables at different frequencies.

## Usage

``` r
trigonometric_variables(frequency, start, length, s, seasonal_frequency = NULL)
```

## Arguments

- frequency:

  Frequency of the series, number of periods per year (12, 4, 3, 2...)

- start, length:

  First date (array with the first year and the first period, for
  instance `c(1980, 1)`) and number of periods of the output variables.
  Can also be provided with the `s` argument

- s:

  time series used to get the dates for the trading days variables. If
  supplied the parameters `frequency`, `start` and `length` are ignored.

- seasonal_frequency:

  the seasonal frequencies. By default the fundamental seasonal
  frequency and all the harmonics are used.

## Value

a mts object with 2 columns

## Details

Denote by \\P\\ the value of `frequency` (= the period) and \\f_1\\,
..., \\f_n\\ the frequencies provides by `seasonal_frequency` (if
`seasonal_frequency = NULL` then \\n=\lfloor P/2\rfloor\\ and
\\f_i\\=i).

`trigonometric_variables` returns a matrix of size \\length\times(2n)\\.

For each date \\t\\ associated to the period \\m\\ (\\m\in\[1,P\]\\),
the columns \\2i\\ and \\2i-1\\ are equal to: \$\$ \cos \left( \frac{2
\pi}{P} \times m \times f_i \right) \text{ and } \sin \left( \frac{2
\pi}{P} \times m \times f_i \right) \$\$ Take for example the case when
the first date (`date`) is a January, `frequency = 12` (monthly time
series), `length = 12` and `seasonal_frequency = NULL`. The first
frequency, \\\lambda_1 = 2\pi /12\\ represents the fundamental seasonal
frequency and the other frequencies (\\\lambda_2 = 2\pi /12 \times 2\\,
..., \\\lambda_6 = 2\pi /12 \times 6\\) are the five harmonics. The
output matrix will be equal to: \$\$ \begin{pmatrix} \cos(\lambda_1) &
\sin (\lambda_1) & \cdots & \cos(\lambda_6) & \sin (\lambda_6) \\
\cos(\lambda_1\times 2) & \sin (\lambda_1\times 2) & \cdots &
\cos(\lambda_6\times 2) & \sin (\lambda_6\times 2)\\ \vdots & \vdots &
\cdots & \vdots & \vdots \\ \cos(\lambda_1\times 12) & \sin
(\lambda_1\times 12) & \cdots & \cos(\lambda_6\times 12) & \sin
(\lambda_6\times 12) \end{pmatrix} \$\$

## Examples

``` r
trigonometric_variables(
    frequency = 12,
    length = 60,
    start = c(2020, 1),
    seasonal_frequency = 12
)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/api/timeseries/TsMoniker has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
