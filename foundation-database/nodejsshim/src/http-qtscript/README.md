# http

This is an emulation of Node.js's `http` package. It wraps Qt's network objects:
 * QNetworkAccessManager
 * QNetworkRequest
 * QNetworkReply
 * QTcpSocket - From our wrapped `net` package.
 * QTcpServer - From our wrapped `net` package.

##See original sources here:
[http](https://github.com/nodejs/node/blob/v4.4.2/lib/http.js)
[_http_client](https://github.com/nodejs/node/blob/v4.4.2/lib/_http_client.js)
[_http_common](https://github.com/nodejs/node/blob/v4.4.2/lib/_http_common.js)
[_http_incoming](https://github.com/nodejs/node/blob/v4.4.2/lib/_http_incoming.js)
[_http_outgoing](https://github.com/nodejs/node/blob/v4.4.2/lib/_http_outgoing.js)
[_http_server](https://github.com/nodejs/node/blob/v4.4.2/lib/_http_server.js)
