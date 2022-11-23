# GOCDB Programmatic Interface - Read

## Method: get_service_group

### Entry point

- `/gocdbpi/public/?method=get_service_group`

| Description | Protection Level |
| - | - |
| Returns a list of service groups and the service endpoints under those groups.  | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `service_group_name`  | Only return info for the service group with specified site name | any service group name | `all` | `?method=get_service_group&service_group_name=Top-BDII` |
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
  <SERVICE_GROUP ID="75123" PRIMARY_KEY="75123G0">
    <NAME>NGI_SI_SERVICES</NAME>
    <DESCRIPTION>NGI_SI Core Services</DESCRIPTION>
    <MONITORED>Y</MONITORED>
    <CONTACT_EMAIL>ops@sling.si</CONTACT_EMAIL>
    <GOCDB_PORTAL_URL>>https://testing.host.com/portal/index.php?Page_Type=View_Object&amp;object_id=119941&amp;grid_id=0</GOCDB_PORTAL_URL>
    <SERVICE_ENDPOINT PRIMARY_KEY="3303G0">
      <HOSTNAME>bdii.ipb.ac.rs</HOSTNAME>
      <GOCDB_PORTAL_URL>https://testing.host.com/portal/index.php?Page_Type=View_Object&amp;object_id=3303&amp;grid_id=0</GOCDB_PORTAL_URL>
      <SERVICE_TYPE>Top-BDII</SERVICE_TYPE>
      <HOST_IP/>
      <HOST_IPV6/>
      <HOSTDN>DC=org/DC=terena/DC=tcs/C=NL/L=Amsterdam/O=Stichting EGI/bdii.ipb.ac.rs</HOSTDN>
      <IN_PRODUCTION>Y</IN_PRODUCTION>
      <NODE_MONITORED>Y</NODE_MONITORED>
      <ENDPOINTS>
        <ENDPOINT>
          <ID>9980</ID>
          <NAME>bdii4.izolamrf.si</NAME>
          <EXTENSIONS/>
          <URL>https://testing.host.com/portal/index.php?Page_Type=View_Object&amp;object_id=9980&amp;grid_id=0</URL>
          <INTERFACENAME>bdii4.izolamrf.si</INTERFACENAME>
          <ENDPOINT_MONITORED>Y</ENDPOINT_MONITORED>
          <CONTACT_EMAIL>contact@izolamrf.co.si</CONTACT_EMAIL>
        </ENDPOINT>
      </ENDPOINTS>
      <SCOPES>
        <SCOPE>EGI</SCOPE>
        <SCOPE>EGICore</SCOPE>
      </SCOPES>
      <EXTENSIONS/>
    </SERVICE_ENDPOINT>
    <SCOPES>
      <SCOPE>EGI</SCOPE>
    </SCOPES>
    <EXTENSIONS/>
  </SERVICE_GROUP>
</results>
```
