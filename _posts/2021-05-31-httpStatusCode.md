---
layout: post
title: HTTP Status Codes
---
**HTTP response status codes**<br>
HTTP response status codes indicate whether a specific HTTP request has been successfully completed. It is a 3-digit integer where the first digit of the status code defines the class of response and the last two digits do not have any categorization.

Responses are grouped in five classes:

- Informational responses (100–199): It means the request has been received and the process is continuing.
- Successful responses (200–299): It means the action was successfully received, understood, and accepted.
- Redirects (300–399): It means further action must be taken in order to complete the request.
- Client errors (400–499): It means the request contains incorrect syntax or cannot be fulfilled.
- Server errors (500–599): It means the server failed to fulfill an apparently valid request.

Below is a list of all the status codes:

 Informational responses (100–199)

 |---|---|
 | Message | Description |
 |100|everything so far is OK and that the client should `continue` the request as long as it has not been rejected |
 |101| indicates that the server is `switching a protocal`|
 
 Successful responses (200–299)

  |---|---|
 | Message | Description |
 |200|The request has completed successfully|
 |201|The request is complete, and a new resource is created|
 |202|The request is accepted for processing, but the processing has not yet started|
 |203|The information in the entity header is from a local or third-party copy, not from the original server(used for mirrors or backups of another resource)|
 |204|A status code and a header are given in the response, but there is no entity-body in the reply|
|205|The browser should clear the form used for this transaction for additional input.|
|206|The server is returning partial data of the size requested|

Redirects (300–399)

