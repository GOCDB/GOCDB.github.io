# GOCDB Programmatic Interface

The GOCDB Programmatic Interface is available under `/gocdbpi`.

It has two main components:

- The [Read API](read/index.md)
- The [Write API](write/index.md)

The Read API provides programmatic access to the data within GOCDB.

The Write API provides limited functionality to add, update, and delete
entities within GOCDB.

## API credential mechanism

Both APIs make use of the API credential mechanism to authenticate/authorise
certain requests.

In order to access these methods, the identifier being used must be in the list
of authorised API credentials for a Site entity. This can be achieved through
the web portal by anyone with a role over a Site that allows them to modify it.

At the bottom of the page showing a site's details is a section titled
"Credentials authorised to use the GOCDB read and write APIs" (this will only
be visible to those who are able to alter sites). Here new identifiers can be added.

## New requests and improvements

New requests and improvements, such as new API methods or parameters, can be
logged via:

- the EGI or EOSC-Future Jira, as appropriate.
- our [GitHub issues](https://github.com/GOCDB/gocdb/issues) page, if the
  above is not appropriate.
