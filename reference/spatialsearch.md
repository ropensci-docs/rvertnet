# Find records within some distance of a point given latitude and longitude.

Searches by decimal latitude and longitude to return any occurrence
record within the input distance (radius) of the input point.

## Usage

``` r
spatialsearch(
  lat,
  long,
  radius,
  limit = 1000,
  compact = TRUE,
  messages = TRUE,
  ...
)
```

## Arguments

- lat:

  (numeric) Latitude of the central point, in decimal degrees required.

- long:

  (numeric) Longitude of the central point, in decimal degrees required.

- radius:

  (numeric) Radius to search, in meters. There is no default value for
  this parameter. required.

- limit:

  (integer) Limit on the number of records returned. If \>1000 results,
  we use a cursor internally, but you should still get up to the results
  you asked for. See also
  [`bigsearch()`](https://docs.ropensci.org/rvertnet/reference/bigsearch.md)
  to get larger result sets in a text file via email.

- compact:

  (logical) Return a compact data frame. default: `TRUE`

- messages:

  (logical) Print progress and information messages. Default: `TRUE`

- ...:

  Curl arguments passed on to
  [crul::HttpClient](https://docs.ropensci.org/crul/reference/HttpClient.html)

## Value

A list with two slots:

- meta: a named list of metadata for the search results

- data: a data frame of search results, columns vary

## Details

`spatialsearch()` finds all records of any taxa having decimal lat/long
coordinates within a given radius (in meters) of your coordinates.

## References

https://github.com/VertNet/webapp/wiki/The-API-search-function

## Examples

``` r
if (FALSE) { # \dontrun{
res <- spatialsearch(lat = 33.529, long = -105.694, radius = 2000,
  limit = 10)

# Pass in curl options for curl debugging
out <- spatialsearch(lat = 33.529, long = -105.694, radius = 2000,
  limit = 10, verbose = TRUE)
} # }
```
