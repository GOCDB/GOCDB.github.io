# GOCDB Programmatic Interface - Read

## Method: get_roc_list

### Entry point

- `/gocdbpi/public/?method=get_roc_list`

| Description | Protection Level |
| - | - |
| Returns a list of NGIs (formerly known as ROCs) with minimal associated information  | Public (level 1) |

### Information

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `roc` | Limit results to given NGI | any NGI name | `all` | `?method=get_roc_list&roc=NGI_SI` |

### Paging

This method does not support paging.

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <ROC PRIMARY_KEY="2G0" ROC_NAME="NGI_CH"/>
  <ROC PRIMARY_KEY="3G0" ROC_NAME="NGI_SI"/>
  <ROC PRIMARY_KEY="4G0" ROC_NAME="NGI_HU"/>
</results>
```
