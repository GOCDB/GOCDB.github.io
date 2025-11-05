# GOCDB Programmatic Interface - Read

## Method: get_cert_status_changes

### Entry point

- `/gocdbpi/private/?method=get_cert_status_changes`

| Description | Protection Level |
| - | - |
| Returns a list of changes/transitions to certification statuses. Note, if the requested Site certification status has never been updated from its initial state, then no changes will have occurred and the results will be empty.  | Private (level 3) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `site` | Only return info for site with specified site name | any site name | `all` | `?method=get_cert_status_changes&site=Izola MRF` |
| `startdate` | Limit results to changes that start after specified date | date in `YYYY-MM-DD` format | none | `?method=get_cert_status_changes&startdate=2022-03-15`  |
| `enddate` | limit results to changes that end before specified date | date in `YYYY-MM-DD` format | none | `?method=get_cert_status_changes&enddate=2022-03-25`  |

### Paging

This method optionally supports paging to iterate over all results,
[see here for info](../optional_cursor_paging.md).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <result ID="1">
    <TIME>13-Sep-2022 09.21.26</TIME>
    <UNIX_TIME>1663060886</UNIX_TIME>
    <SITE>Izola MRF</SITE>
    <OLD_STATUS>Uncertified</OLD_STATUS>
    <NEW_STATUS>Certified</NEW_STATUS>
    <CHANGED_BY>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=Gwei Jai</CHANGED_BY>
    <COMMENT>Site is ready</COMMENT>
  </result>
</results>
```
