# GOCDB Programmatic Interface - Read

## Method: get_roc_contacts

### Entry point

- `/gocdbpi/private/?method=get_roc_contacts`

| Description | Protection Level |
| - | - |
| Returns NGI contact details, including NGI contact mail address and list of NGI staff  | Protected (level 2) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `roc` | Limit results to given NGI | any NGI name | `all` | `?method=get_roc_list&roc=NGI_SI` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <ROC ID="11463" ROC_NAME="NGI_SI">
    <ROCNAME>NGI_SI</ROCNAME>
    <MAIL_CONTACT>ngi-si-contact@swing-grid.si</MAIL_CONTACT>
    <GOCDB_PORTAL_URL>/portal/index.php?Page_Type=NGI&id=11463</GOCDB_PORTAL_URL>
    <CONTACT USER_ID="4322" PRIMARY_KEY="4523G0">
      <FORENAME>Gwei</FORENAME>
      <SURNAME>Jai</SURNAME>
      <TITLE/>
      <EMAIL>Gwei.Jai@izolamrf.si</EMAIL>
      <TEL>+44 040 3636 3600</TEL>
      <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=Gwei Jai</CERTDN>
      <EGICHECKIN>alphanumeric@egi.eu</EGICHECKIN>
      <IRISIAM/>
      <ROLE_NAME>Site Operations Manager</ROLE_NAME>
    </CONTACT>
    <CONTACT USER_ID="468344" PRIMARY_KEY="22434G0">
      <FORENAME>Yuki</FORENAME>
      <SURNAME>Tsunoda</SURNAME>
      <TITLE></TITLE>
      <EMAIL>Yuki.Tsunoda@izolamrf.si</EMAIL>
      <TEL>+49 432 0030 8324</TEL>
      <CERTDN/>
      <EGICHECKIN/>
      <IRISIAM/>
      <ROLE_NAME>Chief Operations Officer</ROLE_NAME>
    </CONTACT>
  </ROC>
</results>
```
