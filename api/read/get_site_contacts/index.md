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
| `sitename` | Only return info for site with specified site name | any site name | `all` | `?method=get_site_contacts&sitename=Izola MRF` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site_contacts&roc=NGI_SI` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site_contacts&country=Slovenia` |
| `roletype` | Only include CONTACTS with the given role | any valid role type | `all` | `?method=get_site_contacts&roletype=Site Operations Manager` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant |  `?method=get_site&scope=EGI` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site_contacts&scope=Local,EGI&scope_match=any` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE ID="14G0" PRIMARY_KEY="119G0" NAME="Izola MRF">
    <PRIMARY_KEY>119G0</PRIMARY_KEY>
    <SHORT_NAME>Izola MRF</SHORT_NAME>
    <CONTACT USER_ID="6G0" PRIMARY_KEY="6G0">
      <FORENAME>Yuki</FORENAME>
      <SURNAME>Tsunoda</SURNAME>
      <TITLE/>
      <EMAIL>Yuki.Tsunoda@izolamrf.si</EMAIL>
      <TEL>+49 432 0030 8324</TEL>
      <CERTDN>/C=00/O=00000/OU=000000/CN=Yuki Tsunoda</CERTDN>
      <ROLE_NAME>Site Operations Manager</ROLE_NAME>
    </CONTACT>
    <CONTACT USER_ID="8G0" PRIMARY_KEY="8G0">
      <FORENAME>Gwei</FORENAME>
      <SURNAME>Jai</SURNAME>
      <TITLE/>
      <EMAIL>Gwei.Jai@izolamrf.si</EMAIL>
      <TEL>+44 040 3636 3600</TEL>
      <CERTDN>/C=00/O=00000/OU=000000/CN=Gwei Jai</CERTDN>
      <ROLE_NAME>Site Operations Deputy Manager</ROLE_NAME>
    </CONTACT>
  </SITE>
</results>
```
