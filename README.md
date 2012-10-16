# Cross-Domain AJAX for IE8

Implements automatic *Cross Origin Resource Sharing* support using the `XDomainRequest` object for IE8 and IE9 when using the [ajax](http://api.jquery.com/jQuery.ajax/) function in jQuery 1.5+.
> **CORS** requires the `Access-Control-Allow-Origin` header to be present in the AJAX response from the server.

In order to use XDomainRequest in Internet Explorer, the request must be:
- asynchronous
- GET or POST
- HTTP or HTTPS
- same scheme as calling page

Working example here:
http://jsfiddle.net/MoonScript/Q7bVG/