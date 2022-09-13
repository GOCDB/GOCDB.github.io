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
  <SERVICE_TYPE TYPE_ID="44G0" PRIMARY_KEY="44G0">
    <SERVICE_TYPE_NAME>egi.GOCDB</SERVICE_TYPE_NAME>
    <SERVICE_TYPE_DESC>[Central Service] The central GOCDB</SERVICE_TYPE_DESC>
  </SERVICE_TYPE>
</results>
```
