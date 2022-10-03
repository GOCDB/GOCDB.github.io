# GOCDB Programmatic Interface - Read

## Method: get_site_contacts

### Entry point

- `/gocdbpi/private/?method=get_site_contacts`

| Description | Protection Level |
| - | - |
| Returns a list of sites nesting contacts having a site level role (if any), grouped per site | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `sitename` | Only return info for site with specified site name | any site name | `all` | `?method=get_site_contacts&sitename=RAL-LCG2` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site_contacts&roc=NGI_DE` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site_contacts&country=Poland` |
| `roletype` | Only include CONTACTS with the given role | any valid role type | `all` | `?method=get_site_contacts&roletype=Site Security Officer` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant |  `?method=get_site&scope=Local` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site_contacts&scope=Local,EGI&scope_match=any` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE ID="335G0" PRIMARY_KEY="123G0" NAME="GRIDOPS-GOCDB">
    <PRIMARY_KEY>123G0</PRIMARY_KEY>
    <SHORT_NAME>GRIDOPS-GOCDB</SHORT_NAME>
    <CONTACT USER_ID="4533G0" PRIMARY_KEY="4533G0">
      <FORENAME>Example</FORENAME>
      <SURNAME>User</SURNAME>
      <TITLE>Mr</TITLE>
      <EMAIL>example.user@stfc.ac.uk</EMAIL>
      <TEL/>
      <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=example user</CERTDN>
      <EGICHECKIN>alphanumeric@egi.eu</EGICHECKIN>
      <IRISIAM/>
      <ROLE_NAME>Site Administrator</ROLE_NAME>
    </CONTACT>
    <CONTACT USER_ID="4533G0" PRIMARY_KEY="4533G0">
      <FORENAME>Example</FORENAME>
      <SURNAME>User</SURNAME>
      <TITLE>Mr</TITLE>
      <EMAIL>example.user@stfc.ac.uk</EMAIL>
      <TEL/>
      <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=example user</CERTDN>
      <EGICHECKIN>alphanumeric@egi.eu</EGICHECKIN>
      <IRISIAM/>
      <ROLE_NAME>Site Operations Manager</ROLE_NAME>
    </CONTACT>
  </SITE>
</results>
```
