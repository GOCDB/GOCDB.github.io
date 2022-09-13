# GOCDB Programmatic Interface - Read

## Method: get_service

### Entry point

- `/gocdbpi/public/?method=get_service`
- `/gocdbpi/public/?method=get_service_endpoint`

| Description | Protection Level |
| - | - |
| Returns a list of service endpoints (single node x single service) and associated information  | Public (level 1) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `hostname` | Limit results to services hosted on node with given hostname | any host name | `all` | `?method=get_service_endpoint&hostname=dcache-tape.gridpp.rl.ac.uk` |
| `sitename` | Only return info for site with specified site name | any site name | `all` |`?method=get_site&sitename=RAL-LCG2` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site&roc=NGI_DE` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site&country=Poland` |
| `service_type` | Limit results to services of given type | any valid ServiceType | `all` | `?method=get_service_endpoint&service_type=CE` |
| `monitored` | Limit results to services hosted on nodes that have monitoring turned on | `Y` or `N` | `all` | `?method=get_service_endpoint&monitored=Y`  |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=Local` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site&scope=Local,EGI&scope_match=any` |
| `extensions` | Limit results by one or many key value pairs | [See Extensions Mechanism](https://docs.egi.eu/internal/configuration-database/extension-properties/) | none | `?method=get_site&extensions=(KeyName=KeyValue)` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

or

This method does not support paging.

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SERVICE_ENDPOINT PRIMARY_KEY="4180G0">
    <PRIMARY_KEY>4180G0</PRIMARY_KEY>
    <HOSTNAME>gocdb.example.com</HOSTNAME>
    <GOCDB_PORTAL_URL>/portal/index.php?Page_Type=Service&id=4180</GOCDB_PORTAL_URL>
    <HOSTDN>/DC=org/DC=terena/DC=tcs/C=NL/L=Amsterdam/O=Stichting EGI/gocdb.example.com</HOSTDN>
    <HOST_ARCH>x86_64</HOST_ARCH>
    <BETA>N</BETA>
    <SERVICE_TYPE>egi.GOCDB</SERVICE_TYPE>
    <CORE/>
    <IN_PRODUCTION>Y</IN_PRODUCTION>
    <NODE_MONITORED>Y</NODE_MONITORED>
    <NOTIFICATIONS>Y</NOTIFICATIONS>
    <SITENAME>GRIDOPS-GOCDB</SITENAME>
    <COUNTRY_NAME>United Kingdom</COUNTRY_NAME>
    <COUNTRY_CODE>GB</COUNTRY_CODE>
    <ROC_NAME>EGI.eu</ROC_NAME>
    <URL>https://gocdb.example.com:443</URL>
    <ENDPOINTS>
      <ENDPOINT>
        <ID>6313</ID>
        <NAME>ProductionPortalInstance</NAME>
        <EXTENSIONS/>
        <URL>https://gocdb.example.com/portal</URL>
        <INTERFACENAME>egi.GOCDB.Portal</INTERFACENAME>
        <ENDPOINT_MONITORED>N</ENDPOINT_MONITORED>
      </ENDPOINT>
      <ENDPOINT>
        <ID>6314</ID>
        <NAME>Production PI base url</NAME>
        <EXTENSIONS/>
        <URL>https://gocdb.example.com/gocdbpi</URL>
        <INTERFACENAME>egi.GOCDB.PI</INTERFACENAME>
        <ENDPOINT_MONITORED>N</ENDPOINT_MONITORED>
      </ENDPOINT>
    </ENDPOINTS>
    <SCOPES>
      <SCOPE>EGI</SCOPE>
      <SCOPE>EGICore</SCOPE>
    </SCOPES>
    <EXTENSIONS/>
  </SERVICE_ENDPOINT>
</results>
```
