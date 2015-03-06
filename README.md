# Cross-Domain AJAX for IE8 and IE9

Implements automatic *Cross Origin Resource Sharing* support using the `XDomainRequest` object for IE8 and IE9 when using the [$.ajax](http://api.jquery.com/jQuery.ajax/) function in jQuery 1.5+.
> **CORS** requires the `Access-Control-Allow-Origin` header to be present in the AJAX response from the server.

In order to use `XDomainRequest` in Internet Explorer, the request must be:
- Only GET or POST
 - When POSTing, the data will always be sent with a `Content-Type` of `text/plain`
- Only HTTP or HTTPS
 - Protocol must be the same scheme as the calling page
- Always asynchronous

Working example here:
http://jsfiddle.net/MoonScript/Q7bVG/show/

## Instructions

With at least jQuery version 1.5, just include the [jquery.xdomainrequest.min.js](http://cdnjs.cloudflare.com/ajax/libs/jquery-ajaxtransport-xdomainrequest/1.0.3/jquery.xdomainrequest.min.js) script into your page, then make your AJAX call like you normally would:

```JavaScript
// GET
$.getJSON('http://jsonmoon.jsapp.us/').done(function(data) {
  console.log(data.name.first);
});

// POST
$.ajax({
  url: 'http://frozen-woodland-5503.herokuapp.com/cors.json',
  data: 'this is data being posted to the server',
  contentType: 'text/plain',
  type: 'POST',
  dataType: 'json'
}).done(function(data) {
  console.log(data.name.last);
});
```

## CDN

This script is hosted by [CDNJS](http://cdnjs.com):

http://cdnjs.cloudflare.com/ajax/libs/jquery-ajaxtransport-xdomainrequest/1.0.3/jquery.xdomainrequest.min.js

## Change log

- **1.0.2** - added RequireJS AMD module support
- **1.0.3** - added CommonJS and Bower support
- **1.0.4** - support protocol-relative URLs, use `peerDependencies` in [package.json](package.json)
