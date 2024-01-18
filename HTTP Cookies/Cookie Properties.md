---
tags:
  - done
---


Some details are important to know about:

1. Cookies are sent with every request made from client (with some exceptions for security reasons).
2. Each cookie has its own scope which is subdivided into two fields: **Domain** and **Path**
	1. Example of a Domain: example.com
	2. Path is a selective route that sends the cookie information . If a cookie has its own `path` set to `/login`, it will send the cookie information only to that specific path automatically.
	3. To set a domain, use `"domain=example.com"`.
3. Expires, Max-age: The default behavior if max-age/expires is not specified is to be destroyed when the browser closes, known as **session cookie**. if max-age/expires is set, then this cookies will turn into **permanent cookies** and will last the time set before be destroyed. Does not matter if the browser closes.
	1. To set the max-age: `max-age=3min`
4. Same site: A example to explain this is... you have clicked into a link that takes you to your bank internet account, forging a request to the bank's services, passing by you. From there, if there is no security against this attack called [[Cross Site Request Forgery (CSRF)]], it will hijack your cookies information, using it to fake your authentication and manipulate the bank's system such as transfer money to another bank account. 
	1. To set Same Site attribute, use: `samesite=strict`.
	2. After set into some attribute, the redirection link can not send your cookie information,  protecting your account, in the bank account example.
	3. To set Same Site attribute to be sent without any protection, use: `samesite=lax`. It is an explicit way to setting the attribute to send by any request. Default Value.