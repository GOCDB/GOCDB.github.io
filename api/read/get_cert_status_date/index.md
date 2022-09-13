# GOCDB Programmatic Interface - Read

## Method: get_cert_status_date

### Entry point

- `/gocdbpi/private/?method=get_cert_status_date`

| Description | Protection Level |
| - | - |
| Returns a list of current certification statuses for `Production` only sites and the date they entered that status | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `certification_status` | Limit results to sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | `all` | `?method=get_site&certification_status=Certified` |
| `roc` | Limit results to given NGI | any NGI name | `all` | `?method=get_roc_list&roc=NGI_DE` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <site ID="40">
    <name>GRIDOPS-GOCDB</name>
    <cert_status>Closed</cert_status>
    <cert_date>14-Jun-22 15.51.32 PM</cert_date>
  </site>
</results>
```
