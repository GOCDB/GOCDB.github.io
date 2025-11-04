# GOCDB Programmatic Interface - Optional Cursor Paging

## Overview

Cursor paging allows clients to iterate through massive result-sets which are
split into one or more smaller pages. This allows result-sets to be processed
that would otherwise be too large or memory-expensive to process in a single
query.

Paging may not always be necessary, we suggest you first try to execute your
query without paging. If the query fails due to breaching of the execution
time or memory limit, then try adding `next_cursor=0`.

Most of the API methods now support optional `next_cursor` and `prev_cursor`
URL parameters.

For backward compatibility, pagination is disabled by default and will only be
enabled when passing one of the new cursor query parameters.

If neither the `next_cursor` or `prev_cursor` URL parameters are specified, the
method behaves as before by fetching/rendering the requested result-set in one
query, and will not add the `meta` element as detailed below.

A non-paged query can therefore fail/timeout if either the execution time or
memory limits are exceeded (e.g. if you make a request for every downtime
without narrowing the search with extra filter parameters).

Paged XML results contain the `meta` element, which contains links to the
current/self, next, previous and first page of results.

When using paging, you need to move forward through the results by reading the
next links until the `count` element hits zero which indicates no more
results are available at that particular moment in time.

To start at the beginning of a result-set, specify `next_cursor=0`.

The max page size has been initially set to 100 but this is subject to change/
refinement. NB: the max page size value is provided in the `max_page_size`
element.

The `count` element shows how many results are on the current page (note, if
this figure is less than `max_page_size` then you have come to the end of
the results, and at that moment in time, the next page will show no results
with a count of zero).

## Summary

### Paging parameters explained

| parameter | definition |
| - | - |
| `next_cursor` | A cursor that points to the start of the next page of results. |
| `prev_cursor` | A cursor that points to the start of the previous page of results. |

### `meta` tags explained

| tag | definition |
| - | - |
| `self` | The link to the current page of results. |
| `next` | The link to the start of the next page of results. |
| `previous` | The link to the start of the previous page of results. |
| `start` | The link to the start of the first page of results. |
| `count` | Shows how many results are on the current page (note, if this figure is less than `max_page_size` then you have come to the end of the results, and at that moment in time, the next page will show no results with a count of zero). |
| `max_page_size` | The maximum number of results shown on a page. |
