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
| `dn` | Limit results to user with given certificate DN | DN in standard string chain format | `all` | `?method=get_user&dn=/C=UK/O=eScience/OU=CLRC/L=RAL/CN=Gwei Jai` |
| `dnlike` | Limit results to user with certificate that matches given wildcard | Search string (SQL syntax) | `all` | `?method=get_user&dnlike=%/OU=CLRC%`  |
| `forename` | Limit results to user(s) with given forename | any string | `all` | `?method=get_user&forename=Gwei` |
| `surname` | Limit results to user(s) with given surname | any string | `all` | `?method=get_user&surname=Jai` |
| `roletype` | Limit results to user(s) with the specified role type(s) | single or comma separated list of role types (multiple roles are combined using OR) | `all` | `?method=get_user&roletype=CIC Staff,Site Operations Manager`  |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
    <EGEE_USER USER_ID="4322G0" PRIMARY_KEY="4523G0">
        <FORENAME>Gwei</FORENAME>
        <SURNAME>Jai</SURNAME>
        <TITLE></TITLE>
        <DESCRIPTION></DESCRIPTION>
        <GOCDB_PORTAL_URL>https://testing.host.com/portal/index.php?Page_Type=View_Object&amp;object_id=6326&amp;grid_id=0</GOCDB_PORTAL_URL>
        <EMAIL>Gwei.Jai@izolamrf.si</EMAIL>
        <TEL>+44 040 3636 3600</TEL>
        <WORKING_HOURS_START></WORKING_HOURS_START>
        <WORKING_HOURS_END></WORKING_HOURS_END>
        <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=Gwei Jai</CERTDN>
        <EGICHECKIN>alphanumeric@egi.eu</EGICHECKIN>
        <IRISIAM/>
        <SSOUSERNAME/>
        <APPROVED/>
        <ACTIVE/>
        <HOMESITE><Izola MRF</HOMESITE>

        <USER_ROLE>
            <USER_ROLE>CIC Staff</USER_ROLE>
            <ON_ENTITY>NGI_SI</ON_ENTITY>
            <ENTITY_TYPE>group</ENTITY_TYPE>
        </USER_ROLE>
        <USER_ROLE>Site Operations Manager</USER_ROLE>
            <USER_ROLE>Site Operations Manager</USER_ROLE>
            <ON_ENTITY>NGI_SI</ON_ENTITY>
            <ENTITY_TYPE>group</ENTITY_TYPE>
        </USER_ROLE>
    </EGEE_USER>
</results>

```
