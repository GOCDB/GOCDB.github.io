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
    <CONTACT USER_ID="4322" PRIMARY_KEY="4523G0">
      <FORENAME>Gwei</FORENAME>
      <SURNAME>Jai</SURNAME>
      <TITLE></TITLE>
      <EMAIL>Gwei.Jai@izolamrf.si</EMAIL>
      <TEL>+44 040 3636 3600</TEL>
      <WORKING_HOURS_START/>
      <WORKING_HOURS_END/>
      <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=Gwei Jai</CERTDN>
      <EGICHECKIN/>
      <IRISIAM/>
      <ROLE_NAME>Site Operations Manager</ROLE_NAME>
    </CONTACT>
  </Project>
</results>
```
