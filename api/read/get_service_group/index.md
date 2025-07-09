# GOCDB Programmatic Interface - Read

## Method: get_service_group

### Entry point

- `/gocdbpi/public/?method=get_service_group`

| Description | Protection Level |
| - | - |
| Returns a list of service groups and the service endpoints under those groups.  | Private (level 3) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `service_group_name`  | Only return info for the service group with specified site name | any service group name | `all` | `?method=get_service_group&service_group_name=NGI_AEGIS_SERVICES` |
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
  <SERVICE_GROUP ID="23" PRIMARY_KEY="23G0">
    <NAME>NGI_AEGIS_SERVICES</NAME>
    <DESCRIPTION>NGI_AEGIS Core Services</DESCRIPTION>
    <MONITORED>Y</MONITORED>
    <CONTACT_EMAIL>grid-admin@ipb.ac.rs</CONTACT_EMAIL>
    <GOCDB_PORTAL_URL>https://localhost/portal/index.php?Page_Type=Service_Group&amp;id=23</GOCDB_PORTAL_URL>
    <SCOPES>
      <SCOPE>EGI</SCOPE>
    </SCOPES>
    <EXTENSIONS/>
  </SERVICE_GROUP>
</results>
```
