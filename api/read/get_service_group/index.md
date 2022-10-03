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
| `service_group_name`  | Only return info for the service group with specified site name | any service group name | `all` | `?method=get_service_group&service_group_name=OPSTOOLS` |
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
  <SERVICE_GROUP ID="690" PRIMARY_KEY="690G0">
    <NAME>A_SERVICE_GROUP</NAME>
    <DESCRIPTION>A ServiceGroup</DESCRIPTION>
    <MONITORED>N</MONITORED>
    <CONTACT_EMAIL>example.user@stfc.ac.uk</CONTACT_EMAIL>
    <GOCDB_PORTAL_URL>/portal/index.php?Page_Type=Service_Group&id=690</GOCDB_PORTAL_URL>
    <SERVICE_ENDPOINT PRIMARY_KEY="4180G0">
      <HOSTNAME>gocdb.example.com</HOSTNAME>
      <GOCDB_PORTAL_URL>/portal/index.php?Page_Type=Service&id=4180</GOCDB_PORTAL_URL>
      <SERVICE_TYPE>egi.GOCDB</SERVICE_TYPE>
      <HOST_IP/>
      <HOST_IPV6/>
      <HOSTDN>DC=org/DC=terena/DC=tcs/C=NL/L=Amsterdam/O=Stichting EGI/gocdb.example.com</HOSTDN>
      <IN_PRODUCTION>Y</IN_PRODUCTION>
      <NODE_MONITORED>Y</NODE_MONITORED>
      <ENDPOINTS>
        <ENDPOINT>
          <ID>6313</ID>
          <NAME>ProductionPortalInstance</NAME>
          <EXTENSIONS/>
          <URL>/portal</URL>
          <INTERFACENAME>egi.GOCDB.Portal</INTERFACENAME>
          <ENDPOINT_MONITORED>N</ENDPOINT_MONITORED>
          <CONTACT_EMAIL>example.user@stfc.ac.uk</CONTACT_EMAIL>
        </ENDPOINT>
      </ENDPOINTS>
      <SCOPES>
        <SCOPE>EGI</SCOPE>
        <SCOPE>EGICore</SCOPE>
      </SCOPES>
      <EXTENSIONS/>
    </SERVICE_ENDPOINT>
    <SCOPES>
      <SCOPE>Local</SCOPE>
    </SCOPES>
    <EXTENSIONS/>
  </SERVICE_GROUP>
</results>
```
