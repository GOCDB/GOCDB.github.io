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
    <CONTACT USER_ID="202G0" PRIMARY_KEY="202G0">
      <FORENAME>Example</FORENAME>
      <SURNAME>User</SURNAME>
      <TITLE>Mr</TITLE>
      <EMAIL>example.user@stfc.ac.uk</EMAIL>
      <TEL>+00 (0) 0000 000000</TEL>
      <WORKING_HOURS_START/>
      <WORKING_HOURS_END/>
      <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=example user</CERTDN>
      <EGICHECKIN/>
      <IRISIAM/>
      <ROLE_NAME>EGI CSIRT Officer</ROLE_NAME>
    </CONTACT>
  </Project>
</results>
```
