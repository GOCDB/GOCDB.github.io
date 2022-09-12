# GOCDB Programmatic Interface - Read

## Releases, changes and announcements

All client tool using the GOCDB Programmatic interface should subscribe to the
GOCDB discussion mailing list: gocdb-discuss_at_mailman.egi.eu. Releases, new
features, changes in methods and general announcements related to this
interface are made on this list.

## Interface description

### Interface type

GOCDB Programmatic Interface is a REST (Representational State Transfer) based
interface over HTTPS. The use of HTTPS guarantees URLs are properly secured
when transiting. Some of the methods are nonetheless public and don't require
client side authentication (see [Data protection levels](#data-protection-levels)).

### Entry point

The GOCDB Programmatic Interface is available under `/gocdbpi`.

### Outputs

Output format is XML. Calling any implemented method will return you a valid
DOM document that can be parsed by any tool on client side.

## Data protection levels

There are currently 3 protection levels for all methods of the interface:

- Level 1: public methods (no security/critical, no personal details, no
otherwise sensitive info)
- Level 2: protected methods (no security/critical, no personal details,
contains otherwise sensitive info)
- Level 3: private methods (contains security/critical information, contains
personal data)

Methods at level 1 are available without restrictions. Methods at level 2
require the client to present a valid credential, such as an IGTF X.509
certificate or a OAuth2 token from a trusted source. Methods at level 3
require the client to present a known credential, registered via the API
credential mechanism.

## Available methods

| Method name | Description | Protection level |
|-|-|-|
get_cert_status_changes |Returns a list of changes to certification statuses | 2
get_cert_status_date | Returns a list of current certification statuses for Production sites and the date they entered that status | 2
[get_downtime](get_downtime/index.md) | Returns a list of service downtimes (downtimes are repeated for each affected service) | 1
get_downtime_nested_services | Returns a list of downtimes with affected services nested as child elements of the downtime | 1
get_downtime_to_broadcast | Returns the list of downtimes recently declared with notification settings for downtime notification services | 1
get_ngi | Returns a list of NGIs with contact information | 2
get_project_contacts | Returns a list of persons (and associated info) having a role over a project. | 2
[get_roc_contacts](get_roc_contacts/index.md) | Returns NGI contact details, including NGI contact mail address and list of NGI staff | 2
[get_roc_list](get_roc_list/index.md) | Returns a list of NGIs with minimal associated information | 1
get_service | Returns a list of services (single node x single service) and associated information (same as get_service_endpoint) | 1
get_service_endpoint | Returns a list of services (single node x single service) and associated information (same as get_service) | 1
get_service_group | Returns a list of service groups and the service endpoints under those groups. | 2
get_service_group_role | Returns a list of service groups and the roles held by users over these groups. | 2
get_service_types | Returns a list of valid service types and associated description | 1
[get_site](get_site/index.md) | Returns site information, grouped by site | 2
[get_site_contacts](get_site_contacts/index.md) | Returns a list of persons (and associated info) having a role at site level, grouped per site | 2
get_site_count_per_country | Returns a count of sites per country (not per NGI) | 1
[get_site_list](get_site_list/index.md) | Returns a list of sites with minimal associated information | 1
[get_site_security_info](get_site_security_info/index.md) | Returns security contact information for sites | 2
get_user | Returns a user or a list of users with associated details and roles | 2
