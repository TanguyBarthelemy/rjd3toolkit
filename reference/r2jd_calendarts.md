# Create Java CalendarTimeSeries

Create Java CalendarTimeSeries

## Usage

``` r
r2jd_calendarts(calendarobs)
```

## Arguments

- calendarobs:

  list.

## Value

a Java object

## Examples

``` r
# example code
obs <- list(
    list(start = as.Date("1980-01-01"), end = as.Date("1999-12-31"), value = 2000),
    list(start = as.Date("2000-01-01"), end = as.Date("2010-01-01"), value = 1000)
)
jobj <- r2jd_calendarts(obs)
#> Error in .jcall("jdplus/toolkit/base/r/timeseries/TsUtility", "Ljdplus/toolkit/base/api/timeseries/CalendarTimeSeries;",     "of", .jarray(starts, "Ljava/lang/String;"), .jarray(ends,         "Ljava/lang/String;"), .jarray(values)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/timeseries/TsUtility has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
