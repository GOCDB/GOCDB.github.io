# GOCDB Programmatic Interface - Read

## Method: get_site

### Entry point

- `/gocdbpi/public/?method=get_site`

### Information

| Description | Protection Level |
| - | - |
| Returns site information including contacts, grouped by site | Protected (level 2) |

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `sitename` | Only return info for site with specified site name | any site name | `all` | `?method=get_site&sitename=Izola MRF` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site&roc=NGI_SI` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site&country=Slovenia` |
| `certification_status` | Limit results to sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | `all` | `?method=get_site&certification_status=Certified` |
| `exclude_certification_status` | Exclude from results sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | none | `?method=get_site&exclude_certification_status=Closed` |
| `production_status` | Limit results to sites within given production infrastructure | one of `Production` or `Test` | `all` | `?method=get_site&production_status=Production` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=EGI` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site&scope=Local,EGI&scope_match=any` |
| `extensions` | Limit results by one or many key value pairs | [See Extensions Mechanism](https://docs.egi.eu/internal/configuration-database/extension-properties/) | none | `?method=get_site&extensions=(KeyName=KeyValue)` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE ID="14" PRIMARY_KEY="119G0" NAME="Izola MRF">
    <PRIMARY_KEY>119G0</PRIMARY_KEY>
    <SHORT_NAME>Izola MRF</SHORT_NAME>
    <OFFICIAL_NAME>Izola Marine Research Facility</OFFICIAL_NAME>
    <SITE_DESCRIPTION>Situated right on Slovenia's small coastline of the Adriatic Sea, the Izola Marine Research Facility is Slovenia's hub for all things ocean research.</SITE_DESCRIPTION>
    <GOCDB_PORTAL_URL>https://localhost/portal/index.php?Page_Type=Site&amp;id=14</GOCDB_PORTAL_URL>
    <HOME_URL>http://www.izolamrf.co.si</HOME_URL>
    <CONTACT_EMAIL>contact@izolamrf.si</CONTACT_EMAIL>
    <CONTACT_TEL>+386 45 310 1393</CONTACT_TEL>
    <GIIS_URL>ldap://grid.izolamrf.si:0000/ds-vo-name=IzolaMRF,o=grid</GIIS_URL>
    <COUNTRY_CODE>SI</COUNTRY_CODE>
    <COUNTRY>Slovenia</COUNTRY>
    <ROC>NGI_SI</ROC>
    <PRODUCTION_INFRASTRUCTURE>Test</PRODUCTION_INFRASTRUCTURE>
    <CERTIFICATION_STATUS>Certified</CERTIFICATION_STATUS>
    <TIMEZONE>UTC</TIMEZONE>
    <LATITUDE>45.541431</LATITUDE>
    <LONGITUDE>13.662742</LONGITUDE>
    <CSIRT_EMAIL>csirt@izolamrf.si</CSIRT_EMAIL>
    <NOTIFICATIONS>FALSE</NOTIFICATIONS>
    <DOMAIN>
      <DOMAIN_NAME>izolamrf.si</DOMAIN_NAME>
    </DOMAIN>
    <SITE_IP>0.0.0.0/255.255.255.255</SITE_IP>
    <SCOPES>
      <SCOPE>EGI</SCOPE>
    </SCOPES>
    <EXTENSIONS/>
  </SITE>
</results>
```
