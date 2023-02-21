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
| `hostname` | Limit results to services hosted on node with given hostname | any host name | `all` | `?method=get_service_endpoint&hostname=bdii.ipb.ac.rs` |
| `sitename` | Only return info for site with specified site name | any site name | `all` |`?method=get_site&sitename=Izola MRF` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site&roc=NGI_SI` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site&country=Slovenia` |
| `service_type` | Limit results to services of given type | any valid ServiceType | `all` | `?method=get_service_endpoint&service_type=ARC-CE` |
| `monitored` | Limit results to services hosted on nodes that have monitoring turned on | `Y` or `N` | `all` | `?method=get_service_endpoint&monitored=Y`  |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=EGI` |
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
  <SERVICE_ENDPOINT PRIMARY_KEY="1G0">
    <PRIMARY_KEY>1G0</PRIMARY_KEY>
    <HOSTNAME>lodur.torchit.ch</HOSTNAME>
    <GOCDB_PORTAL_URL>https://localhost/portal/index.php?Page_Type=Service&id=1</GOCDB_PORTAL_URL>
    <HOSTDN>/DC=com/DC=quovadisglobal/DC=grid/DC=Torch/DC=hosts/C=CH/ST=Zuerich/L=Zuerich/O=SWITCH/CN=lodur.torchit.ch</HOSTDN>
    <HOST_OS>SL5</HOST_OS>
    <HOST_ARCH>64 bit</HOST_ARCH>
    <BETA>N</BETA>
    <SERVICE_TYPE>Local-LFC</SERVICE_TYPE>
    <HOST_IP>130.59.111.49</HOST_IP>
    <CORE/>
    <IN_PRODUCTION>N</IN_PRODUCTION>
    <NODE_MONITORED>N</NODE_MONITORED>
    <NOTIFICATIONS>N</NOTIFICATIONS>
    <SITENAME>Torch</SITENAME>
    <COUNTRY_NAME>Switzerland</COUNTRY_NAME>
    <COUNTRY_CODE>CH</COUNTRY_CODE>
    <ROC_NAME>NGI_CH</ROC_NAME>
    <URL/>
    <ENDPOINTS>
      <ENDPOINT>
        <ID>1</ID>
        <NAME>sampleEndpoint</NAME>
        <EXTENSIONS/>
        <URL/>
        <INTERFACENAME>Local-LFC</INTERFACENAME>
        <ENDPOINT_MONITORED>N</ENDPOINT_MONITORED>
      </ENDPOINT>
    </ENDPOINTS>
    <SCOPES>
      <SCOPE>Local</SCOPE>
    </SCOPES>
    <EXTENSIONS/>
  </SERVICE_ENDPOINT>
</results>
```
