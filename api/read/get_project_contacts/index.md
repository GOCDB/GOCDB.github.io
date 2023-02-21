# GOCDB Programmatic Interface - Read

## Method: get_project_contacts

### Entry point

- `/gocdbpi/public/?method=get_project_contacts`

| Description | Protection Level |
| - | - |
| Returns a list of persons (and associated info) having a role over a project.  | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `project` | Limit results to users with a role over a specified project | any project name | `all` | `?method=get_project_contacts&project=EGI` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <Project ID="1" NAME="EGI">
    <CONTACT USER_ID="8G0" PRIMARY_KEY="8G0">
      <FORENAME>Gwei</FORENAME>
      <SURNAME>Jai</SURNAME>
      <TITLE/>
      <EMAIL>Gwei.Jai@izolamrf.si</EMAIL>
      <TEL>+44 040 3636 3600</TEL>
      <WORKING_HOURS_START/>
      <WORKING_HOURS_END/>
      <CERTDN>/C=00/O=00000/OU=000000/CN=Gwei Jai</CERTDN>
      <ROLE_NAME>COD Staff</ROLE_NAME>
    </CONTACT>
    <CONTACT USER_ID="9G0" PRIMARY_KEY="9G0">
      <FORENAME>G</FORENAME>
      <SURNAME>Wiz</SURNAME>
      <TITLE/>
      <EMAIL>G.Wiz@brunnengs.ch</EMAIL>
      <TEL>+44 220 4244 4335</TEL>
      <WORKING_HOURS_START/>
      <WORKING_HOURS_END/>
      <CERTDN>/C=00/O=00000/OU=000000/CN=G Wiz</CERTDN>
      <ROLE_NAME>COD Staff</ROLE_NAME>
    </CONTACT>
  </Project>
</results>
```
