# krb-proxies #

This repository contains proxies for HTTP and HTTPS transport of Kerberos
traffic.  These are segregated currently into two parts:

## server-side ##

This contains the server-side proxy that turns HTTP traffic into Kerberos and
kpasswd traffic.  It is written as a
[Python WSGI](http://www.python.org/dev/peps/pep-0333/) program, suitable for
use with HTTPS-equipped Apache using mod_wsgi (or theoretically any other web
server that supports WSGI).

## client-side ##

For development reasons, client-side code is currently separated into HTTPS
and plain HTTP.

### client-side-http ###

The HTTP-only code requires glib2 for base64 support.  It defaults to
listening on port 88, and to POSTing to / on port 80.

### client-side-https ###

The HTTPS-only code also requires glib2 for the same reason as above, but it
also make use of OpenSSL for HTTPS support.  It should support SSLv2, SSLv3,
and TLSv1.  As with the HTTP-only code, it defaults to listening on port 88,
and to POSTing to /, but on port 443.
