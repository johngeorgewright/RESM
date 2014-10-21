HTTP vs Web Sockets
===================

Transport over HTTP is very different to that over a web socket. A HTTP request comes bundled with method names, paths and optional content. A HTTP request is also followed directly by a response containg a status code and optional content.

A web socket message contains only content... and there is no response. This leads to a very different approach when transferring states.

