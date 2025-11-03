# GOCDB Programmatic Interface - Read

## Method: get_roc_contacts

### Entry point

- `/gocdbpi/private/?method=get_roc_contacts`

| Description | Protection Level |
| - | - |
| Returns NGI contact details, including NGI contact mail address and list of NGI staff  | Private (level 3) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `roc` | Limit results to given NGI | any NGI name | `all` | `?method=get_roc_list&roc=NGI_SI` |

### Paging

This method optionally supports paging to iterate over all results,
[see here for info](../optional_cursor_paging.md).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <ROC ID="3" ROC_NAME="NGI_SI">
    <ROCNAME>NGI_SI</ROCNAME>
    <MAIL_CONTACT>ngi-si-contact@swing-grid.si</MAIL_CONTACT>
    <GOCDB_PORTAL_URL>https://localhost/portal/index.php?Page_Type=NGI&amp;id=3</GOCDB_PORTAL_URL>
    <CONTACT USER_ID="8G0" PRIMARY_KEY="8G0">
      <FORENAME>Gwei</FORENAME>
      <SURNAME>Jai</SURNAME>
      <TITLE/>
      <EMAIL>Gwei.Jai@izolamrf.si</EMAIL>
      <TEL>+44 040 3636 3600</TEL>
      <CERTDN>/C=00/O=00000/OU=000000/CN=Gwei Jai</CERTDN>
      <ROLE_NAME>Regional Staff (ROD)</ROLE_NAME>
    </CONTACT>
    <CONTACT USER_ID="10G0" PRIMARY_KEY="10G0">
      <FORENAME>Dante</FORENAME>
      <SURNAME>Meloni</SURNAME>
      <TITLE/>
      <EMAIL>Dante.Meloni@ssc.si</EMAIL>
      <TEL>+01 040 0331 3231</TEL>
      <CERTDN>/C=00/O=00000/OU=000000/CN=Dante Meloni</CERTDN>
      <ROLE_NAME>Regional Staff (ROD)</ROLE_NAME>
    </CONTACT>
  </ROC>
</results>
```
