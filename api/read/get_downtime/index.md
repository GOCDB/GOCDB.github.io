# GOCDB Programmatic Interface - Read

## Method: get_downtime

### Entry point

- `/gocdbpi/public/?method=get_downtime&ongoing_only=yes`

| Description | Protection Level |
| - | - |
| Returns a list of service downtimes with each downtime duplicated for each affected service.  | Public (level 1) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `topentity` | Limit results to downtimes below given entity | any NGI (ROC), country, site name or node hostname | none | `?method=get_downtime&topentity=RAL-LCG2` |
| `ongoing_only` | Limit results to current ongoing downtimes | `yes` or `no` | `no` | `?method=get_downtime&ongoing_only=yes` |
| `startdate` | Limit results to downtimes that start after specified date | date in `YYYY-MM-DD` format | none | `?method=get_downtime&startdate=2021-12-08`  |
| `enddate` | Limit results to downtimes that end before specified date | date in `YYYY-MM-DD` format | none | `?method=get_downtime&enddate=2021-12-14`  |
| `windowstart`/`windowend` | Limit results to downtimes that cross into the time window (includes downtimes that start before or end after window) | dates in `YYYY-MM-DD` format | none | `?method=get_downtime&windowstart=2021-12-08&windowend=2021-12-15` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=Local` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site&scope=Local,EGI&scope_match=any` |
| `site_extensions` | Limit results by one or many key value pairs | [See Extensions Mechanism](https://docs.egi.eu/internal/configuration-database/extension-properties/) | none | `?method=get_site&site_extensions=(KeyName=KeyValue)` |
| `service_extensions` | Limit results by one or many key value pairs | [See Extensions Mechanism](https://docs.egi.eu/internal/configuration-database/extension-properties/) | none | `?method=get_site&service_extensions=(KeyName=KeyValue)` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <DOWNTIME ID="32578" PRIMARY_KEY="113653G0" CLASSIFICATION="SCHEDULED">
    <PRIMARY_KEY>113653G0</PRIMARY_KEY>
    <HOSTNAME>host.example.com</HOSTNAME>
    <SERVICE_TYPE>egi.GOCDB</SERVICE_TYPE>
    <ENDPOINT>endpoint.example.stfc.ac.uk</ENDPOINT>
    <HOSTED_BY>GRIDOPS-GOCDB</HOSTED_BY>
    <GOCDB_PORTAL_URL>/portal/index.php?Page_Type=Downtime&id=32578</GOCDB_PORTAL_URL>
    <AFFECTED_ENDPOINTS/>
    <SEVERITY>WARNING</SEVERITY>
    <DESCRIPTION>The service will be at risk</DESCRIPTION>
    <INSERT_DATE>1656137042</INSERT_DATE>
    <START_DATE>1656288000</START_DATE>
    <END_DATE>1688169600</END_DATE>
    <FORMATED_START_DATE>2022-06-27 00:00</FORMATED_START_DATE>
    <FORMATED_END_DATE>2023-07-01 00:00</FORMATED_END_DATE>
  </DOWNTIME>
</results>
```
