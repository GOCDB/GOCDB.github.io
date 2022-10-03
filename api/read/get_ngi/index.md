# GOCDB Programmatic Interface - Read

## Method: get_ngi

### Entry point

- `/gocdbpi/private/?method=get_ngi`

| Description | Protection Level |
| - | - |
| Returns a list of NGIs with contact information | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site&roc=NGI_DE` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=Local` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site&scope=Local,EGI&scope_match=any` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <NGI ID="35" NAME="NGI_UK">
    <PRIMARY_KEY>35</PRIMARY_KEY>
    <NAME>NGI_UK</NAME>
    <OBJECT_ID>35</OBJECT_ID>
    <DESCRIPTION>United Kingdom NGI</DESCRIPTION>
    <EMAIL>email@example.com</EMAIL>
    <GGUS_SU>NGI_UK</GGUS_SU>
    <ROD_EMAIL>email@example.com</ROD_EMAIL>
    <HELPDESK_EMAIL/>
    <SECURITY_EMAIL>email@example.com</SECURITY_EMAIL>
    <SITE_COUNT>60</SITE_COUNT>
    <SCOPES>
      <SCOPE>EGI</SCOPE>
    </SCOPES>
  </NGI>
</results>

```
