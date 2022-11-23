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
| `roletype` | Only include CONTACTS with the given role | any valid role type | `all` | `?method=get_site_contacts&roletype=Site Security Officer` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant |  `?method=get_site&scope=EGI` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` | `?method=get_site_contacts&scope=Local,EGI&scope_match=any` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE ID="119G0" PRIMARY_KEY="119G0" NAME="Izola Marine Research Facility">
    <PRIMARY_KEY>119G0</PRIMARY_KEY>
    <SHORT_NAME>Izola MRF</SHORT_NAME>
    <CONTACT USER_ID="4322G0" PRIMARY_KEY="4322G0">
      <FORENAME>Gwei</FORENAME>
      <SURNAME>Jai</SURNAME>
      <TITLE></TITLE>
      <EMAIL>Gwei.Jai@izolamrf.si</EMAIL>
      <TEL>+44 040 3636 3600</TEL>
      <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=Gwei Jai</CERTDN>
      <EGICHECKIN>alphanumeric@egi.eu</EGICHECKIN>
      <IRISIAM/>
      <ROLE_NAME>Site Operations Manager</ROLE_NAME>
    </CONTACT>
    <CONTACT USER_ID="468344G0" PRIMARY_KEY="22434G0">
      <FORENAME>Yuki</FORENAME>
      <SURNAME>Tsunoda</SURNAME>
      <TITLE></TITLE>
      <EMAIL>Yuki.Tsunoda@izolamrf.si</EMAIL>
      <TEL>+49 432 0030 8324</TEL>
      <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=Yuki Tsunoda</CERTDN>
      <EGICHECKIN></EGICHECKIN>
      <IRISIAM/>
      <ROLE_NAME>Chief Operations Officer</ROLE_NAME>
    </CONTACT>
  </SITE>
</results>
```
