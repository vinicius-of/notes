---
tags:
  - done
---

1. Session Cookie
	1. A default cookie. This type does not contain max-age or expires. When you close the browser, the cookie will be deleted.
	   
2. Permanent Cookie
	1. A cookie that has a max-age attribute set. When the time comes, it will be deleted from web application. However, this type is not deleted when the browser is closed.
	   
3. HttpOnly Cookie
	1. Cookies that can only be set from the server. The client-side/browser can not read the information that this cookie contains from the DOM (document object).
	2. To set this attribute, just set into your server response: `jsCanNotSeeThis=1; httponly`.
	3. You can see the attribute set into the console.
	   
4. Secure Cookie
	1. Cookies that can only be sent to HTTPS domains.
	2. [[How to Set A Secure Cookie]]
	   
5. Third Party Cookie
6. Zombie Cookie
	1. Cookies that recreate themselves with the prior value based on other information.
	2. HTTP Caching [[E-tags]]
