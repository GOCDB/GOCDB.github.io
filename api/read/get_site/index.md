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
| `sitename` | Only return info for site with specified site name | any site name | `all` | `?method=get_site&sitename=RAL-LCG2` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site&roc=NGI_DE` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site&country=Poland` |
| `certification_status` | Limit results to sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | `all` | `?method=get_site&certification_status=Certified` |
| `exclude_certification_status` | Exclude from results sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | none | `?method=get_site&exclude_certification_status=Closed` |
| `production_status` | Limit results to sites within given production infrastructure | one of `Production` or `Test` | `all` | `?method=get_site&production_status=Production` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=Local` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site&scope=Local,EGI&scope_match=any` |
| `extensions` | Limit results by one or many key value pairs | [See Extensions Mechanism](https://docs.egi.eu/internal/configuration-database/extension-properties/) | none | `?method=get_site&extensions=(KeyName=KeyValue)` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE ID="335" PRIMARY_KEY="123G0" NAME="GRIDOPS-GOCDB">
    <PRIMARY_KEY>123G0</PRIMARY_KEY>
      <SHORT_NAME>GRIDOPS-GOCDB</SHORT_NAME>
      <OFFICIAL_NAME>Grid Operations Center Database Portal and Web Services</OFFICIAL_NAME>
      <SITE_DESCRIPTION>The GOCDB stores Grid topology and resource information for EGI including sites, services, downtimes and contact information.</SITE_DESCRIPTION>
      <GOCDB_PORTAL_URL>/portal/index.php?Page_Type=Site&id=335</GOCDB_PORTAL_URL>
      <HOME_URL>https://example.stfc.ac.uk</HOME_URL>
      <CONTACT_EMAIL>example@mailman.egi.eu</CONTACT_EMAIL>
      <CONTACT_TEL>+00 (0) 0000 000000</CONTACT_TEL>
      <COUNTRY_CODE>GB</COUNTRY_CODE>
      <COUNTRY>United Kingdom</COUNTRY>
      <ROC>EGI.eu</ROC>
      <PRODUCTION_INFRASTRUCTURE>Production</PRODUCTION_INFRASTRUCTURE>
      <CERTIFICATION_STATUS>Certified</CERTIFICATION_STATUS>
      <TIMEZONE>Europe/London</TIMEZONE>
      <CSIRT_EMAIL>example@mailman.egi.eu</CSIRT_EMAIL>
      <NOTIFICATIONS>TRUE</NOTIFICATIONS>
      <DOMAIN>
        <DOMAIN_NAME>example.stfc.ac.uk</DOMAIN_NAME>
      </DOMAIN>
      <SITE_IP>0.0.0.0/255.255.255.254</SITE_IP>
      <SCOPES>
        <SCOPE>EGI</SCOPE>
        <SCOPE>EOSC-hub</SCOPE>
        <SCOPE>iris.ac.uk</SCOPE>
        <SCOPE>EGICore</SCOPE>
      </SCOPES>
    <EXTENSIONS/>
  </SITE>
</results>
```
