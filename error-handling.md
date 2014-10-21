Error Handling
==============

Request Error Codes
-------------------

Request errors are created by fault of the requester.

```json
{
  "type": "request error",
  "data": 4
}
```

<dl>
  <dt>0 Bad Request</dt>
  <dd>The request cannot be fulfilled due to bad syntax.</dd>

  <dt>1 Unauthorized</dt>
  <dd>Authentication is required and has failed or has not yet been provided.</dd>

  <dt>2 Payment Required</dt>
  <dd>The request cannot be fulfilled until a payment is made.</dd>

  <dt>3 Forbidden</dt>
  <dd>The requested resource could not be found but may be available again in the future. Subsequent requests by the client are permissible.</dd>

  <dt>4 Not Found</dt>
  <dd>The requested resource could not be found but may be available again in the future.</dd>

  <dt>5 Message Type Not Allowed</dt>
  <dd>A request was made of a resource using a message type not supported by that resource.</dd>

  <dt>9 Conflict</dt>
  <dd>Indicates that the request could not be processed because of conflict in the request, such as an edit conflict in the case of multiple updates.</dd>

  <dt>10 Gone</dt>
  <dd>Indicates that the resource requested is no longer available and will not be available again.</dd>

  <dt>12 Precondition Failed</dt>
  <dd>The server does not meet one of the preconditions that the requester put on the request.</dd>

  <dt>15 Unsupported Media Type</dt>
  <dd>The request entity has a media type which the server or resource does not support. For example, the client uploads an image as image/svg+xml, but the server requires that images use a different format.</dd>

  <dt>19 Authentication Timeout</dt>
  <dd>Indications that you the requester was once authorized, but is no longer due to inactivity</dd>

  <dt>22 Unprocessable Entity</dt>
  <dd>The request was well-formed but was unable to be followed due to semantic errors.</dd>

  <dt>23 Locked</dt>
  <dd>The resource that is being accessed is locked.</dd>

  <dt>24 Failed Dependency</dt>
  <dd>The request failed due to failure of a previous request.</dd>

  <dt>25 Upgrade Required</dt>
  <dd>Switch to a newer version of the API</dd>

  <dt>28 Precondition Required</dt>
  <dd>The origin server requires the request to be conditional.</dd>

  <dt>29 Too Many Requests</dt>
  <dd>The user has sent too many requests in a given amount of time.</dd>

  <dt>51 Unavailable For Legal Reasons</dt>
  <dd>Intended to be used when resource access is denied for legal reasons, e.g. censorship or government-mandated blocked access.</dd>
</dl>

Processing Error Codes
----------------------

Processing errors are generated when there was a problem giving back a result from a request.

```json
{
  "type": "processing error",
  "data": 0
}
```

<dl>
  <dt>0 Internal Error</dt>
  <dd>A generic error message, given when an unexpected condition was encountered and no more specific message is suitable.</dd>

  <dt>3 Service Unavilable</dt>
  <dd>The server is currently unavailable (because it is overloaded or down for maintenance).</dd>

  <dt>7 Insufficient Storage</dt>
  <dd>The server is unable to store the representation needed to complete the request.</dd>

  <dt>8 Loop Detected</dt>
  <dd>A loop in message emitting and receiving has been detected.</dd>
</dl>


