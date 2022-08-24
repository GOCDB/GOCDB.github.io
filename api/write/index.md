# GOCDB Programmatic Interface - Write

## Authentication/Authorisation

The Write API requires the client to present a known credential, registered
via the API credential mechanism.

In order to make changes to a Site, Service or Service Endpoint entity (or
there extension properties), the identifier being used must be in the list of
authorised credentials for the relevant Site.

## Supported methods

The following tables list the methods supported in the Write API, and the
associated paths.

### Services

This section covers manipulating Service entities.

| HTTP Method | URL [see [Note 4](#notes)]  | Request Body | Function |
| - | - | - | - |
| POST | `/gocdbpi/v5/Service/<ServiceID>/<ServicePropertyName>` | Property value in JSON Format e.g. [Note 2](#notes) | For the service with the specified ID, updates the specified property. Fails if the property is already defined. Not a valid method for mandatory or boolean fields. |
| PUT | `/gocdbpi/v5/Service/<ServiceID>/<ServicePropertyName>` | Property value in JSON Format e.g. [Note 2](#notes) | For the service with the specified ID, updates the specified property, overwriting any existing value with the one specified. |

### Service Endpoints

This section covers manipulating Service Endpoint entities.

| HTTP Method | URL [see [Note 6](#notes)] | Request Body | Function |
| - | - | - | - |
| POST | `/gocdbpi/v5/Service/<ServiceID>/Endpoint` | End point in JSON format e.g. Note 5 | Adds a new end point to the service with the specified ID with the values specified in the request body. If an endpoint with the specified name already exists for the specified service then the operation fails. |
| PUT | `/gocdbpi/v5/Service/<ServiceID>/Endpoint` | End point in JSON format e.g. Note 5 | Adds a new end point to the service with the specified ID with the values specified in the request body. If an endpoint with the specified name already exists for the specified service then it will be overwritten with new values for each field specified. |
| DELETE | `/gocdbpi/v5/Service/<ServiceID>/Endpoint/<EndpointID>` | None or empty | Deletes the specified endpoint. If there is no endpoint with that ID or it doesn't belong to the specified service the operation will fail. |
| POST | `/gocdbpi/v5/Endpoint/<EndpointID>/<EndpointPropertyName>` | Property value in JSON Format e.g. [Note 2](#notes) | For the end point with the specified ID, updates the specified property. Fails if the property is already defined. Not a valid method for mandatory or boolean fields. |
| PUT | `/gocdbpi/v5/Endpoint/<EndpointID>/<EndpointPropertyName>` | Property value in JSON Format e.g. [Note 2](#notes) | For the end point with the specified ID, updates the specified property, overwriting any existing value with the one specified. |

### Extension Properties

This section covers manipulating extensions properties belonging to various
entities.

#### Site

| HTTP Method | Paths | Request Body | Function |
| - | - | - | - |
| POST | `/gocdbpi/v5/Site/<SiteID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | Adds the extension properties defined in the request to the Site with the given ID (fails if extension properties already exist with any of the specified property names). |
| PUT | `/gocdbpi/v5/Site/<SiteID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | For the site with the specified ID, adds the specified properties, overwriting any existing ones with the specified names (If none of them are currently defined, the it is functionally equivalent to POST). |
| DELETE | `/gocdbpi/v5/Site/<SiteID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | Removes all the extension properties specified in the request body for the identified site (fails if any of the listed properties are not currently defined. Note: values do not have to be defined, an empty string can be provided instead. If a value is provided, it must be correct. See Note 3 for examples. |
| DELETE | `/gocdbpi/v5/Site/<SiteID>/ExtensionProperties` | None or empty | Removes all the extension properties for the identified site. |
| POST | `/gocdbpi/v5/Site/<SiteID>/ExtensionProperties/<PropertyName>` | Value in JSON Format e.g [Note 2](#notes) | Adds an extension property to the identified site with the given name and value in the request (fails if property with that name is already defined). |
| PUT | `/gocdbpi/v5/Site/<SiteID>/ExtensionProperties/<PropertyName>` | Value in JSON Format e.g [Note 2](#notes) | Adds an extension property to the identified site, overwriting any exiting property with the given name (If none of that name is already defined, then it is functionally equivalent to POST). |
| DELETE | `/gocdbpi/v5/Site/<SiteID>/ExtensionProperties/<PropertyName>` | None or empty or Value in JSON Format e.g [Note 2](#notes) | Removes the named extension property from the named site (fails if request body is present and the value does not match the current value of the property or if the named property is not defined for the identified Site). |

#### Service

| HTTP Method | URL | Request Body | Function |
| - | - | - | - |
| POST | `/gocdbpi/v5/Service/<ServiceID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | Adds the extension properties defined in the request to the service with the given ID (fails if any of the extension properties are already defined). |
| PUT | `/gocdbpi/v5/Service/<ServiceID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | For the service with the specified ID, adds the specified properties, overwriting any existing ones with the specified names (If none of them are currently defined, the it is functionally equivalent to POST). |
| DELETE | `/gocdbpi/v5/Service/<ServiceID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | Removes all the extension properties specified in the request body for the identified service (fails if any of the listed properties are not currently defined). Note: values do not have to be defined, an empty string can be provided instead. If a value is provided, it must be correct. See Note 3 for examples. |
| DELETE | `/gocdbpi/v5/Service/<ServiceID>/ExtensionProperties` | None or empty | Removes all the extension properties for the identified service. |
| POST | `/gocdbpi/v5/Service/<ServiceID>/ExtensionProperties/<PropertyName>` | Value in JSON Format e.g [Note 2](#notes) | Adds an extension property to the identified service with the given name and value in the request (fails if property with that name is already defined). |
| PUT | `/gocdbpi/v5/Service/<ServiceID>/ExtensionProperties/<PropertyName>` | Value in JSON Format e.g [Note 2](#notes) | Adds an extension property to the identified service, overwriting any exiting property with the given name (If none of that name is already defined, then it is functionally equivalent to POST). |
| DELETE | `/gocdbpi/v5/Service/<ServiceID>/ExtensionProperties/<PropertyName>` | None or empty or Value in JSON Format e.g [Note 2](#notes) | Removes the named extension property from the named service (fails if request body is present and the value does not match the current value of the property or if the named property is not defined for the identified Service). |

#### Service Endpoint

| HTTP Method | URL | Request Body | Function|
| - | - | - | - |
| POST | `/gocdbpi/v5/Endpoint/<EndpointID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | Adds the extension properties defined in the request to the SE with the given ID  (fails if any of the extension properties are already defined). |
| PUT | `/gocdbpi/v5/Endpoint/<EndpointID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | For the SE with the specified ID, adds the specified properties, overwriting any existing ones with the specified names (If none of them are currently defined, the it is functionally equivalent to POST). |
| DELETE | `/gocdbpi/v5/Endpoint/<EndpointID>/ExtensionProperties` | Key value pairs in JSON Format e.g. Note 1 | Removes all the extension properties specified in the request body for the identified SE (fails if any of the listed properties are not currently defined). Note: values do not have to be defined, an empty string can be provided instead. If a value is provided, it must be correct. See Note 3 for examples. |
| DELETE | `/gocdbpi/v5/Endpoint/<EndpointID>/ExtensionProperties` | None or empty | Removes all the extension properties for the identified SE. |
| POST | `/gocdbpi/v5/Endpoint/<EndpointID>/ExtensionProperties/<PropertyName>` | Value in JSON Format e.g [Note 2](#notes)| Adds an extension property to the identified SE with the given name and value in the request (fails if property with that name is already defined). |
| PUT | `/gocdbpi/v5/Endpoint/<EndpointID>/ExtensionProperties/<PropertyName>` | Value in JSON Format e.g [Note 2](#notes) | Adds an extension property to the identified SE, overwriting any exiting property with the given name (If none of that name is already defined, then it is functionally equivalent to POST). |
| DELETE | `/gocdbpi/v5/Endpoint/<EndpointID>/ExtensionProperties/<PropertyName>` | None or empty or Value in JSON Format e.g [Note 2](#notes) | Removes the named extension property from the named SE (fails if request body is present and the value does not match the current value of the property or if the named property is not defined for the identified SE). |

## Examples

An example command using 'PUT' to update extension properties for a site:

```bash
$ curl -i \
  --cacert </path/to/CA/Cert/pem> \
  --cert </path/to/personal/cert/pem> \
  --key <path/to/personal/cert/key/pem> \
  -X PUT /gocdbpi/V5/site/335/ExtensionProperties \
  -d '{
      "isAwesome": "True",
      "Volume": "11"
  }'
```

This example will only work if the certificate provided is authorised to alter
the site with id 335 (see
[Authentication/Authorisation](#authenticationauthorisation)).

- The `-i` option returns the whole header, allowing the user to see the HTTP
response code.
- The `-d` option allows you to specify the data for the message request body.
For the write API, this will always be in JSON format.
- The `-k` option can be used for testing to disable authentication of the
host, but should not be used in a production setting.

An example command using `DELETE` to remove all the extension properties from
a site:

```bash
$ curl -i \
  --cacert </path/to/CA/Cert/pem> \
  --cert </path/to/personal/cert/pem> \
  --key <path/to/personal/cert/key/pem> \
  -X DELETE /gocdbpi/V5/site/335/ExtensionProperties \
```

As before, this example will only work if the certificate provided is
authorised to alter the Site with id 335 (see
[Authentication/Authorisation](#authenticationauthorisation)).

- No data is required for `DELETE` methods, and so the `-d` option is not used.

## Notes

1.
    ```yaml
    [
        {
            "PROPERTY1NAME": "PROPERTY1VALUE",
            "PROPERTY2NAME": "PROPERTY2VALUE",
            "PROPERTY3NAME": true
        }
    ]
    ```

1.
    ```yaml
    [
        {
            "value": "PROPERTYVALUE"
        }
    ]
    ```

1. For DELETE methods, the following are functionally equivalent

    ```yaml
    [
        {
            "PROPERTY1NAME": "PROPERTY1VALUE",
            "PROPERTY2NAME": "PROPERTY2VALUE",
            "PROPERTY3NAME": "PROPERTY3VALUE"
        }
    ]
    ```

    and

    ```yaml
    [
        {
            "PROPERTY1NAME": "",
            "PROPERTY2NAME": "",
            "PROPERTY3NAME": ""
        }
    ]
    ```

1. Properties for service that can be updated are (case-insensitive):
    - Mandatory properties
      - `Hostname`
      - `Email`
    - Boolean properties (see [Note 1](#notes))
        - `Production`
        - `Beta`
        - `Monitored`
        - `Notify`
    - Other properties
      - `Description`
      - `host_dn`
      - `Host_IP`
      - `Host_IP_V6`
      - `Host_OS`
      - `Host_Arch`
      - `URL`

1.
    ```yaml
    [
        {
            "name": "ENDPOINTNAME",
            "url": "ENDPOINTURL",
            "interfaceName": "INTERFACENAME",
            "description": "ENDPOINTDESCRIPTION",
            "email": "EMAILADDRESS",
            "monitored": boolean
        }
    ]
    ```

    - `name` is mandatory.
    - `url` is mandatory for POST requests and PUT requests where there is no
      existing endpoint with the given name for the given service. If no
      'interfacename' is provided then the service type of the parent service
      will be used by default.
    - If no value is specified for 'monitored' the current 'monitored' value
      of the parent service will be used by default.

1. Properties for an endpoint that can be updated are (case-insensitive):
    - `Name`
    - `URL`
    - `InterfaceName`
    - `Description`
    - `Email`
    - `Monitored`
