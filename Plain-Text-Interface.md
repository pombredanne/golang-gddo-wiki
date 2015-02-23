GoDoc provides plain text output for integration with shell scripts. Use the HTTP Accept header to request a plain text response.

Search for packages with the term 'sql':

    $ curl -H 'Accept: text/plain' http://godoc.org/?q=sql

Get the documentation for the standard math package:

    $ curl -H 'Accept: text/plain' http://godoc.org/math
