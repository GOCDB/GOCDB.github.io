# GOCDB Programmatic Interface - Read

## Method: get_site_security_info

### Entry point

- `/gocdbpi/private/?method=get_site_security_info`

| Description | Protection Level |
| - | - |
| Returns security/CSIRT contact information for sites | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `sitename` | Only return info for site with specified site name | any site name | `all` | `?method=get_site_security_info&sitename=RAL-LCG2` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site_security_info&roc=NGI_DE` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site_security_info&country=Poland` |
| `certification_status` | Limit results to sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | `all` | `?method=get_site&certification_status=Certified` |
| `exclude_certification_status` | Exclude from results sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | none | `?method=get_site&exclude_certification_status=Closed` |
| `production_status` | Limit results to sites within given production infrastructure | one of `Production` or `Test` | `all` | `?method=get_site&production_status=Production` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=Local` |
| `scope_match` | Match 'all' or 'any' of the specified scope-tags | 'all' or 'any' | `all` | `?method=get_site_security_info&scope=Local,EGI&scope_match=any` |

### Paging

This method does not support paging.

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE ID="335G0" PRIMARY_KEY="123G0" NAME="GRIDOPS-GOCDB">
    <PRIMARY_KEY>123G0</PRIMARY_KEY>
    <SHORT_NAME>GRIDOPS-GOCDB</SHORT_NAME>
    <CSIRT_EMAIL>example@mailman.egi.eu</CSIRT_EMAIL>
    <CSIRT_TEL>+00 (0) 0000 000000</CSIRT_TEL>
  </SITE>
</results>
```
