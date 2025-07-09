# GOCDB Programmatic Interface - Read

## Method: get_downtime_to_broadcast

### Entry point

- `/gocdbpi/private/?method=get_downtime_to_broadcast`

| Description | Protection Level |
| - | - |
| Returns the list of downtimes recently declared with notification settings | Public (level 1) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `interval` | Limit results to downtimes that have been inserted in the past interval days | number | 1 | `?method=get_downtime_to_broadcast&interval=7` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=Local` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site&scope=Local,EGI&scope_match=any` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <DOWNTIME ID="32893" PRIMARY_KEY="119G0" CLASSIFICATION="SCHEDULED">
    <PRIMARY_KEY>119G0</PRIMARY_KEY>
    <SITENAME>Izola MRF</SITENAME>
    <HOSTNAME>izolamrf.co.si</HOSTNAME>
    <SERVICE_TYPE>bdii4.izolamrf.si</SERVICE_TYPE>
    <HOSTED_BY>Izola MRF</HOSTED_BY>
    <GOCDB_PORTAL_URL>/portal/index.php?Page_Type=Downtime&amp;id=32893</GOCDB_PORTAL_URL>
    <AFFECTED_ENDPOINTS/>
    <SEVERITY>WARNING</SEVERITY>
    <DESCRIPTION>The service will be at risk</DESCRIPTION>
    <INSERT_DATE>1662983065</INSERT_DATE>
    <START_DATE>1663660800</START_DATE>
    <END_DATE>1663668000</END_DATE>
    <REMINDER_START_DOWNTIME>1663574400</REMINDER_START_DOWNTIME>
    <BROADCASTING_START_DOWNTIME/>
  </DOWNTIME>
</results>
```
