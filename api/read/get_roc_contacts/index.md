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
| `roc` | Limit results to given NGI | any NGI name | `all` | `?method=get_roc_list&roc=NGI_DE` |

### Paging

This method optionally supports paging, to iterate over all results,
[see here for info](https://wiki.egi.eu/wiki/GOCDB/notifications#Optional_Cursor_Paging_on_Read_API).

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <ROC ID="4" ROC_NAME="EGI.eu">
    <ROCNAME>EGI.eu</ROCNAME>
    <MAIL_CONTACT>example@egi.eu</MAIL_CONTACT>
    <GOCDB_PORTAL_URL>/portal/index.php?Page_Type=NGI&id=4</GOCDB_PORTAL_URL>
    <CONTACT USER_ID="406G0" PRIMARY_KEY="406G0">
      <FORENAME>Example</FORENAME>
      <SURNAME>User</SURNAME>
      <TITLE/>
      <EMAIL>example.user@stfc.ac.uk</EMAIL>
      <TEL>+00 (0) 0000 000000</TEL>
      <CERTDN>/C=UK/O=eScience/OU=CLRC/L=RAL/CN=example user</CERTDN>
      <EGICHECKIN/>
      <IRISIAM/>
      <ROLE_NAME>Regional Staff (ROD)</ROLE_NAME>
    </CONTACT>
    <CONTACT USER_ID="6079G0" PRIMARY_KEY="6079G0">
      <FORENAME>Example</FORENAME>
      <SURNAME>User</SURNAME>
      <TITLE>Dr</TITLE>
      <EMAIL>example.user@stfc.ac.uk</EMAIL>
      <TEL/>
      <CERTDN/>
      <EGICHECKIN>alphanumeric@egi.eu</EGICHECKIN>
      <IRISIAM/>
      <ROLE_NAME>Regional Staff (ROD)</ROLE_NAME>
    </CONTACT>
  </ROC>
</results>
```
