---
layout: post
title: HTTP Status Codes
---

**HTTP response status codes**<br>
HTTP response status codes indicate whether a specific [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) request has been successfully completed. It is a 3-digit integer where the first digit of the status code defines the class of response and the last two digits do not have any categorization.[(HTTP - Status Codes)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

Responses are grouped in five classes:

- Informational responses (100–199): It means the request has been received and the process is continuing.
- Successful responses (200–299): It means the action was successfully received, understood, and accepted.
- Redirects (300–399): It means further action must be taken in order to complete the request.
- Client errors (400–499): It means the request contains incorrect syntax or cannot be fulfilled.
- Server errors (500–599): It means the server failed to fulfill an apparently valid request.

Below is a list of some common http status codes:

**Informational responses (100–199)**

|---|---|
| Message | Description |
|100|everything so far is OK and that the client should continue the request as long as it has not been rejected |
|101| indicates that the server is switching a protocal|

**Successful responses (200–299)**

|---|---|
| Message | Description |
|200|The request has completed successfully|
|201|The request is complete, and a new resource is created|
|202|The request is accepted for processing, but the processing has not yet started|
|203|The information in the entity header is from a local or third-party copy, not from the original server(used for mirrors or backups of another resource)|
|204|A status code and a header are given in the response, but there is no entity-body in the reply|
|205|The browser should clear the form used for this transaction for additional input.|
|206|The server is returning partial data of the size requested|

**Redirect responses (300–399)**

|---|---|
| Message | Description |
|300|A link list where a user can select a link and go to that location|
|301|The requested page has moved to a new url|
|302|The requested page has moved and found at a temporary new url|
|303|The requested page can be found under a different url|
|305|The requested URL must be accessed through the proxy mentioned in the Location header|
|307|The requested page has moved temporarily to a new url|

**Client errors (400–499)**

|---|---|
| Message | Description |
|400|The server did not understand the request(bad request)|
|401|The requested page needs a username and a password(unauthorised)|
|403|Access is forbidden to the requested page|
|404|The server can not find the requested page|
|405|The method specified in the request is not allowed|
|408|The request took longer than the server was prepared to wait|
|409|The request could not be completed because of a conflict.|
|410|The requested page is no longer available|

**Server errors (500–599)**

|---|---|
| Message | Description |
|500|The request was not completed because the server encountered a situation it doesn't know how to handle|
|501|The request method is not supported by the server and cannot be handled|
|502|The request was not completed because the server received an invalid response from the upstream server|
|503|The server is not ready to handle the request|
|504|The gateway has timed out|
|505|The server does not support the "http protocol" version|