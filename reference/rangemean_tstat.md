# Range-Mean Regression

Function to perform a range-mean regression, trimmed to avoid outlier
distortion. The can be used to select whether the original series will
be transformed into log or maintain in level.

## Usage

``` r
rangemean_tstat(data, period = 0, groupsize = 0, trim = 0)
```

## Arguments

- data:

  data to test.

- period:

  periodicity of the data.

- groupsize:

  number of observations per group (before being trimmed). The default
  group size (`groupsize = 0`) is computed as followed:

  - if `period = 12` or `period = 6`, it is equal to `12`;

  - if `period = 4` it is equal to `12` if the data has at least 166
    observations, `8` otherwise;

  - if `period = 3` or `period = 2` it is equal to `12` if the data has
    at least 166 observations, `6` otherwise;

  - if `period = 1` it is equal to `9` if the data has at least 166
    observations, `5` otherwise;

  - it is equal to `period` otherwise.

- trim:

  number of trimmed observations.

## Value

T-Stat of the slope of the range-mean regression.

## Details

First, the data is divided into \\n\\ groups of successive observations
of length \\l\\ (`groupsize`). That is, the first group is formed with
the first \\l\\ observations, the second group is formed with
observations \\1+l\\ to \\2l\\, etc. Then, for each group \\i\\, the
observations are sorted and the `trim` smallest and largest observations
are rejected (to avoid outlier distortion). With the other observations,
the range (noted \\y_i\\) and mean (noted \\m_i\\) are computed.

Finally, the following regression is performed : \$\$ y_t = \alpha +
\beta m_t + u_t. \$\$ The function `rangemean_tstat` returns the
T-statistic associated to \\\beta\\. If it is significantly higher than
0, log transformation is recommended.

## Examples

``` r
y <- ABS$X0.2.09.10.M
# Multiplicative pattern
plot(y)

period <- 12
rm_t <- rangemean_tstat(y, period = period, groupsize = period)
#> Error in .jcall("jdplus/toolkit/base/r/modelling/AutoModelling", "D",     "rangeMean", as.numeric(data), as.integer(period), as.integer(groupsize),     as.integer(trim)): RcallMethod: cannot determine object class
rm_t # higher than 0
#> Error: object 'rm_t' not found
# Can be tested:
pt(rm_t, period - 2, lower.tail = FALSE)
#> Error: object 'rm_t' not found
# Or :
1 - cdf_t(period - 2, rm_t)
#> Error in .jcall("jdplus/toolkit/base/r/stats/Distributions", "[D", "cdfT",     df, .jarray(as.numeric(x))): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/modelling/AutoModelling has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0

# Close to 0
rm_t_log <- rangemean_tstat(log(y), period = period, groupsize = period)
#> Error in .jcall("jdplus/toolkit/base/r/modelling/AutoModelling", "D",     "rangeMean", as.numeric(data), as.integer(period), as.integer(groupsize),     as.integer(trim)): RcallMethod: cannot determine object class
rm_t_log
#> Error: object 'rm_t_log' not found
pt(rm_t_log, period - 2, lower.tail = FALSE)
#> Error: object 'rm_t_log' not found
```
