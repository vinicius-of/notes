---
tags:
  - done
---

There are two ways to create cookies:

1) Javascript - Document.cookie
2) Web Server - Set-cookie header

To create a cookie from client-side/ using Javascript:

1. Access example.com from your browser
2. Open the console from Developer Tools
3. Code

```javascript
	document.cookie="hussein=2"
```

To create a cookie from server-side:

1. From your server application, you can set the cookie from any request or endpoint.
2. To set the cookie to your client, set the `set-cookie` header into your HTTP request.
3. The cookie setup need to follow a kind of key/value format.
	1. 
```
	"sessionId=1234567"
```

Next page: [[Cookie Properties]]
