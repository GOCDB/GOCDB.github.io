# GOCDB Programmatic Interface - Read

## Method: get_service_group_role

### Entry point

- `/gocdbpi/private/?method=get_service_group_role`

| Description | Protection Level |
| - | - |
| Returns a list of service groups and the roles under those groups.  | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `service_group_name` | Only return info for the service group with specified site name | any ServiceGroup name | `all` | `?method=get_service_group_role&service_group_name=Top-BDII` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=EGI` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site&scope=Local,EGI&scope_match=any` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SERVICE_GROUP ID="75123" PRIMARY_KEY="75123G0">
    <NAME>NGI_SI_SERVICES</NAME>
    <DESCRIPTION>NGI_SI Core Servicea</DESCRIPTION>
    <MONITORED>Y</MONITORED>
    <CONTACT_EMAIL>ops@sling.si</CONTACT_EMAIL>
    <GOCDB_PORTAL_URL>https://testing.host.com/portal/index.php?Page_Type=View_Object&amp;object_id=119941&amp;grid_id=0</GOCDB_PORTAL_URL>
    <USER>
      <FORENAME>Dejan</FORENAME>
      <SURNAME>Lesjak</SURNAME>
      <CERTDN>/C=SI/O=SiGNET/O=IJS/OU=F9/CN=Dejan Lesjak</CERTDN>
      <EGICHECKIN/>
      <IRISIAM/>
      <GOCDB_PORTAL_URL>https://testing.host.com/portal/index.php?Page_Type=View_Object&amp;object_id=7729&amp;grid_id=0</GOCDB_PORTAL_URL>
      <ROLE>Service Group Administrator</ROLE>
    </USER>
  </SERVICE_GROUP>
</results>
```
