# GOCDB Programmatic Interface - Read

## Method: get_service_types

### Entry point

- `/gocdbpi/public/?method=get_service_types`

| Description | Protection Level |
| - | - |
| Returns a list of valid service types and associated description | Public (level 1) |

### Information

This method does not support any parameters.

### Paging

This method does not support paging.

### Example Output

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SERVICE_TYPE TYPE_ID="1G0" PRIMARY_KEY="1G0">
    <SERVICE_TYPE_NAME>CE</SERVICE_TYPE_NAME>
    <SERVICE_TYPE_DESC>[Site service] The LCG Compute Element. Currently the standard CE within the gLite middleware stack. Soon to be replaced by the CREAM CE. </SERVICE_TYPE_DESC>
  </SERVICE_TYPE>
</results>
```
