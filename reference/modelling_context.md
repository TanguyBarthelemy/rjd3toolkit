# Create modelling context

Function allowing to include calendars and external regressors in a
format that makes them usable in an estimation process (reg-arima or
tramo modelling, stand alone or as pre-processing in seasonal
adjustment). The regressors can be created with functions available in
the package or come from any other source, provided they are `ts` class
objects.

## Usage

``` r
modelling_context(calendars = NULL, variables = NULL)
```

## Arguments

- calendars:

  list of calendars.

- variables:

  list of variables.

## Value

list of calendars and variables

## References

More information on auxiliary variables in JDemetra+ online
documentation: <https://jdemetra-new-documentation.netlify.app/>

## See also

[`add_usrdefvar`](https://rjdverse.github.io/rjd3toolkit/reference/add_usrdefvar.md),
[`intervention_variable`](https://rjdverse.github.io/rjd3toolkit/reference/intervention_variable.md)

## Examples

``` r
# Creating one or several external regressors (TS objects), which will
# be gathered in one or several groups
iv1 <- intervention_variable(12, c(2000, 1), 60,
    starts = "2001-01-01", ends = "2001-12-01"
)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/stats/Tests has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
iv2 <- intervention_variable(12, c(2000, 1), 60,
    starts = "2001-01-01", ends = "2001-12-01", delta = 1
)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/TsDomain;",     "of", as.integer(period), as.integer(startYear), as.integer(startPeriod),     as.integer(length)): RcallMethod: cannot determine object class

# Regressors as a list of two groups reg1 and reg2
vars <- list(reg1 = list(x = iv1), reg2 = list(x = iv2))
#> Error: object 'iv1' not found

# Creating the modelling context
my_context <- modelling_context(variables = vars)
#> Error: object 'vars' not found
```
