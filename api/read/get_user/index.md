# GOCDB Programmatic Interface - Read

## Method: get_user

### Entry point

- `/gocdbpi/private/?method=get_user`

| Description | Protection Level |
| - | - |
| Returns a user or a list of users with associated details and roles. Note that roles apply to a particular project – this is shown in the XML which qualifies which user-roles apply to which project using the RECOGNISED_IN_PROJECTS element. | Private (level 3) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `dn` | Limit results to user with given certificate DN | DN in standard string chain format | `all` | `?method=get_user&dn=/C=UK/O=eScience/OU=CLRC/L=RAL/CN=Gwei Jai` |
| `dnlike` | Limit results to user with certificate that matches given wildcard | Search string (SQL syntax) | `all` | `?method=get_user&dnlike=%/OU=CLRC%`  |
| `forename` | Limit results to user(s) with given forename | any string | `all` | `?method=get_user&forename=Gwei` |
| `surname` | Limit results to user(s) with given surname | any string | `all` | `?method=get_user&surname=Jai` |
| `roletype` | Limit results to user(s) with the specified role type(s) | single or comma separated list of role types (multiple roles are combined using OR) | `all` | `?method=get_user&roletype=CIC Staff,Site Operations Manager`  |

### Paging

This method optionally supports paging to iterate over all results,
[see here for info](../optional_cursor_paging.md).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <EGEE_USER ID="8G0" PRIMARY_KEY="8G0">
    <FORENAME>Gwei</FORENAME>
    <SURNAME>Jai</SURNAME>
    <TITLE/>
    <DESCRIPTION/>
    <GOCDB_PORTAL_URL>https://localhost/portal/index.php?Page_Type=User&amp;id=8</GOCDB_PORTAL_URL>
    <EMAIL>Gwei.Jai@izolamrf.si</EMAIL>
    <TEL>+44 040 3636 3600</TEL>
    <WORKING_HOURS_START/>
    <WORKING_HOURS_END/>
    <CERTDN>/C=00/O=00000/OU=000000/CN=Gwei Jai</CERTDN>
    <SSOUSERNAME/>
    <APPROVED/>
    <ACTIVE/>
    <HOMESITE>Izola MRF</HOMESITE>
    <USER_ROLE>
      <USER_ROLE>Site Operations Deputy Manager</USER_ROLE>
      <ON_ENTITY>Izola MRF</ON_ENTITY>
      <ENTITY_TYPE>site</ENTITY_TYPE>
      <PRIMARY_KEY>119G0</PRIMARY_KEY>
      <RECOGNISED_IN_PROJECTS>
        <PROJECT ID="1">EGI</PROJECT>
      </RECOGNISED_IN_PROJECTS>
    </USER_ROLE>
    <USER_ROLE>
      <USER_ROLE>Regional Staff (ROD)</USER_ROLE>
      <ON_ENTITY>NGI_SI</ON_ENTITY>
      <ENTITY_TYPE>ngi</ENTITY_TYPE>
      <PRIMARY_KEY>3</PRIMARY_KEY>
      <RECOGNISED_IN_PROJECTS>
        <PROJECT ID="1">EGI</PROJECT>
      </RECOGNISED_IN_PROJECTS>
    </USER_ROLE>
    <USER_ROLE>
      <USER_ROLE>COD Staff</USER_ROLE>
      <ON_ENTITY>EGI</ON_ENTITY>
      <ENTITY_TYPE>project</ENTITY_TYPE>
      <PRIMARY_KEY>1</PRIMARY_KEY>
      <RECOGNISED_IN_PROJECTS>
        <PROJECT ID="1">EGI</PROJECT>
      </RECOGNISED_IN_PROJECTS>
    </USER_ROLE>
  </EGEE_USER>
</results>
```
