# GOCDB Programmatic Interface - Read

## Method: get_site_list

### Entry point

- `/gocdbpi/public/?method=get_site_list`

### Information

| Description | Protection Level |
| - | - |
| Returns a list of sites with minimal associated information | Public (level 1) |

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `sitename` | Only return info for site with specified site name | any site name | `all` | `?method=get_site_list&sitename=Izola MRF` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site_list&roc=NGI_SI` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site_list&country=Slovenia` |
| `certification_status` | Limit results to sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | `all` |  `?method=get_site&certification_status=Certified` |
| `exclude_certification_status` | Exclude from results sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | none |  `?method=get_site&exclude_certification_status=Closed` |
| `production_status` | Limit results to sites within given production infrastructure | one of `Production` or `Test` | `all` |  `?method=get_site&production_status=Production` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant |  `?method=get_site&scope=EGI` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` |  `?method=get_site_list&scope=Local,EGI&scope_match=any` |
| `extensions` | Limit results by one or many key value pairs | [See Extensions Mechanism](https://docs.egi.eu/internal/configuration-database/extension-properties/) | none |  `?method=get_site&extensions=(KeyName=KeyValue)` |

### Paging

This method does not support paging.

### Output_Example

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE ID="11" PRIMARY_KEY="523G0" NAME="BERNUNI-GRID" COUNTRY="Switzerland" COUNTRY_CODE="CH" ROC="NGI_CH" SUBGRID="" GIIS_URL="ldap://bernuni-grid.ch:0000/ds-vo-name=BERNUNI-GRID,o=grid"/>
  <SITE ID="12" PRIMARY_KEY="200G0" NAME="Basel Infrastructure" COUNTRY="Switzerland" COUNTRY_CODE="CH" ROC="NGI_CH" SUBGRID="" GIIS_URL=""/>
  <SITE ID="13" PRIMARY_KEY="351G0" NAME="SSC" COUNTRY="Slovenia" COUNTRY_CODE="SI" ROC="NGI_SI" SUBGRID="" GIIS_URL="ldap://grid.ssc.si:0000/ds-vo-name=SSC,o=grid"/>
  <SITE ID="14" PRIMARY_KEY="119G0" NAME="Izola MRF" COUNTRY="Slovenia" COUNTRY_CODE="SI" ROC="NGI_SI" SUBGRID="" GIIS_URL="ldap://grid.izolamrf.si:0000/ds-vo-name=IzolaMRF,o=grid"/>
</results>
```
