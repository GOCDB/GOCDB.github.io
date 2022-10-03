# GOCDB Programmatic Interface - Read

## Method: get_user

### Entry point

- `/gocdbpi/private/?method=get_user`

| Description | Protection Level |
| - | - |
| Returns a user or a list of users with associated details and roles. Note that roles apply to a particular project – this is shown in the XML which qualifies which user-roles apply to which project using the RECOGNISED_IN_PROJECTS element. | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `dn` | Limit results to user with given certificate DN | DN in standard string chain format | `all` | `?method=get_user&dn=/C=UK/O=eScience/OU=CLRC/L=RAL/CN=example user` |
| `dnlike` | Limit results to user with certificate that matches given wildcard | Search string (SQL syntax) | `all` | `?method=get_user&dnlike=%/OU=ngi.org%`  |
| `forename` | Limit results to user(s) with given forename | any string | `all` | `?method=get_user&forename=Robert` |
| `surname` | Limit results to user(s) with given surname | any string | `all` | `?method=get_user&surname=Smith` |
| `roletype` | Limit results to user(s) with the specified role type(s) | single or comma separated list of role types (multiple roles are combined using OR) | `all` | `?method=get_user&roletype=EGI CSIRT Officer,Chief Operations Officer`  |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <EGEE_USER ID="4533G0" PRIMARY_KEY="4533G0">
    <FORENAME>Example</FORENAME>
    <SURNAME>User</SURNAME>
    <TITLE>Mr</TITLE>
    <DESCRIPTION/>
    <GOCDB_PORTAL_URL>/index.php?Page_Type=User&id=4533</GOCDB_PORTAL_URL>
    <EMAIL>example.user@stfc.ac.uk</EMAIL>
    <TEL/>
    <WORKING_HOURS_START/>
    <WORKING_HOURS_END/>
    <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=example user</CERTDN>
    <EGICHECKIN>alphanumeric@egi.eu</EGICHECKIN>
    <IRISIAM/>
    <SSOUSERNAME/>
    <APPROVED/>
    <ACTIVE/>
    <HOMESITE/>
    <USER_ROLE>
      <USER_ROLE>Site Security Officer</USER_ROLE>
      <ON_ENTITY>GRIDOPS-GOCDB</ON_ENTITY>
      <ENTITY_TYPE>site</ENTITY_TYPE>
      <PRIMARY_KEY>140G0</PRIMARY_KEY>
      <RECOGNISED_IN_PROJECTS>
        <PROJECT ID="1">EGI</PROJECT>
      </RECOGNISED_IN_PROJECTS>
    </USER_ROLE>
    <USER_ROLE>Site Operations Manager</USER_ROLE>
      <ON_ENTITY>EOSC_Core_Topology</ON_ENTITY>
      <ENTITY_TYPE>site</ENTITY_TYPE>
      <PRIMARY_KEY>113086G0</PRIMARY_KEY>
      <RECOGNISED_IN_PROJECTS>
        <PROJECT ID="3091">EOSCCore</PROJECT>
      </RECOGNISED_IN_PROJECTS>
    </USER_ROLE>
  </EGEE_USER>
</results>

```
