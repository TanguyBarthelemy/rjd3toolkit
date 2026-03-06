# Display Easter Sunday dates in given period

Allows to display the date of Easter Sunday for each year, in the
defined period. Dates are displayed in "YYYY-MM-DD" format and as a
number of days since January 1st 1970.

## Usage

``` r
easter_dates(year0, year1, julian = FALSE)
```

## Arguments

- year0, year1:

  starting year and ending year

- julian:

  Boolean indicating if Julian calendar must be used.

## Value

a named numeric vector. Names are the dates in format "YYYY-MM-DD",
values are number of days since January 1st 1970.

## References

More information on calendar correction in JDemetra+ online
documentation:
<https://jdemetra-new-documentation.netlify.app/a-calendar-correction>

## See also

[`national_calendar`](https://rjdverse.github.io/rjd3toolkit/reference/national_calendar.md),
[`easter_day`](https://rjdverse.github.io/rjd3toolkit/reference/easter_day.md)

## Examples

``` r
# Dates from 2018(included) to 2023 (included)
easter_dates(2018, 2023)
#> Error in .jcall("jdplus/toolkit/base/r/calendar/Calendars", "[S", "easter",     as.integer(year0), as.integer(year1), as.logical(julian)): java.lang.UnsupportedClassVersionError: jdplus/toolkit/base/r/modelling/Differencing has been compiled by a more recent version of the Java Runtime (class file version 65.0), this version of the Java Runtime only recognizes class file versions up to 61.0
```
