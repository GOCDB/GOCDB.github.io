# GOCDB Programmatic Interface - Read

## Method: get_site_count_per_country

### Entry point

- `/gocdbpi/public/?method=get_site_count_per_country`

| Description | Protection Level |
| - | - |
| Returns a list of countries with site count | Public (level 1) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `certification_status` | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | none | `?method=get_site&exclude_certification_status=Closed` |
| `production_status` | Limit results to sites within given production infrastructure | one of `Production` or `Test` | `all` | `?method=get_site&production_status=Production` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=EGI` |

### Paging

This method does not support paging.

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE>
    <COUNTRY>Hungary</COUNTRY>
    <COUNT>6</COUNT>
  </SITE>
  <SITE>
    <COUNTRY>Slovenia</COUNTRY>
    <COUNT>4</COUNT>
  </SITE>
  <SITE>
    <COUNTRY>Switzerland</COUNTRY>
    <COUNT>8</COUNT>
  </SITE>
</results>
```
