# GOCDB Programmatic Interface - Read

## Method: get_ngi

### Entry point

- `/gocdbpi/private/?method=get_ngi`

| Description | Protection Level |
| - | - |
| Returns a list of NGIs with contact information | Private (level 3) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site&roc=NGI_SI` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant | `?method=get_site&scope=EGI` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site&scope=Local,EGI&scope_match=any` |

### Paging

This method optionally supports paging to iterate over all results,
[see here for info](../optional_cursor_paging.md).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <NGI ID="3" NAME="NGI_SI">
    <PRIMARY_KEY>3</PRIMARY_KEY>
    <NAME>NGI_SI</NAME>
    <OBJECT_ID>3</OBJECT_ID>
    <DESCRIPTION>An NGI based in Slovenia.</DESCRIPTION>
    <EMAIL>ngi-si-contact@swing-grid.si</EMAIL>
    <GGUS_SU/>
    <ROD_EMAIL/>
    <HELPDESK_EMAIL>ngi-si-helpdesk@swing-grid.si</HELPDESK_EMAIL>
    <SECURITY_EMAIL>ngi-si-security@swing-grid.si</SECURITY_EMAIL>
    <SITE_COUNT>4</SITE_COUNT>
    <SCOPES>
      <SCOPE>EGI</SCOPE>
    </SCOPES>
  </NGI>
</results>
```
