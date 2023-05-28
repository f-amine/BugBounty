# How the Internet Works

### The Client-Server Model
![1dd6ba4e2508024b3309fdf89acb95ff.png](/_resources/1dd6ba4e2508024b3309fdf89acb95ff.png)

### The Domain Name System

![e4d6d09df6f8b31405d8638491337089.png](../_resources/e4d6d09df6f8b31405d8638491337089.png)

### Internet Ports

![2856f47d038fcb55d10c288cefaec7a4.png](../_resources/2856f47d038fcb55d10c288cefaec7a4.png)

### HTTP Requests and Responses

HTTP is a set of rules that specifies how to structure and interpret internet messages, and how web clients and web servers should exchange information:
- GET requests retrieve data from the server, while POST requests submit data to it.
- OPTIONS, used to request permitted HTTP methods for a given URL
- PUT, used to update a resource
- DELETE, used to delete a resource.

example of GET HTTP request

![1d8a4c6486a24c7870840cdb482369db.png](../_resources/1d8a4c6486a24c7870840cdb482369db.png)

Examples of HTTP headers:

- Accept: Specifies the MIME types that the client can handle.
- Authorization: Contains the credentials to authenticate a user agent with a server.
- Cache-Control: Specifies directives for caching mechanisms in both requests and responses.
- Content-Type: Indicates the media type of the resource.
- Cookie: Contains stored HTTP cookies previously sent by the server with the Set-Cookie header.
- User-Agent: Contains information about the user agent originating the request.

example of HTTP Response:
![9e9f86a4c2f9bd82bf2d865ec51e010c.png](../_resources/9e9f86a4c2f9bd82bf2d865ec51e010c.png)

### Internet Security Controls !

**1- Content Encoding**
- HTTP requests and responses can be encoded to prevent data corruption during transmission. Base64 and hex encoding are common methods used to transport binary data reliably across machines. URL encoding is used to convert characters into a format that is more easily transmitted over the internet. Octal and dword encoding are additional types of character encoding. Servers may also encrypt their content before transmission to keep the data private between the client and server. Decoding encoded content can be done using tools like Burp Suite's decoder or CyberChef.

**2- Session Management and HTTP Cookies**

![7eea6623cd3405139a7bea2d115c286e.png](../_resources/7eea6623cd3405139a7bea2d115c286e.png)


![ccae9cc0558e39111520e913908c3127.png](../_resources/ccae9cc0558e39111520e913908c3127.png)

**3- Token-Based Authentication**
In session-based authentication, the server stores your information and uses a
corresponding session ID to validate your identity, whereas a token-based authen-
tication system stores this info directly in some sort of token. Instead of storing
your information server-side and querying it using a session ID, tokens allow
servers to deduce your identity by decoding the token itself. This way, applica-
tions won’t have to store and maintain session information server-side.
**4- JSON Web Tokens**

JSON Web Tokens (JWT) are commonly used authentication tokens that have three components: a header, a payload, and a signature. The header identifies the algorithm used to generate the signature, the payload contains information about the user's identity, and the signature validates that the user hasn't tampered with the token. When implemented correctly, JWTs provide a secure way to identify the user, but if implemented incorrectly, attackers can bypass the security mechanism and forge arbitrary tokens.
**5- The same origin policy**
The Same-Origin Policy (SOP) is a rule that restricts how a script from one origin can interact with the resources of a different origin. Two URLs are said to have the same origin if they share the same protocol, hostname, and port number. The SOP protects modern web applications and prevents many common web vulnerabilities. The SOP prevents a script from page A from accessing data from page B unless the pages are of the same origin. The SOP protects users from malicious scripts that might try to retrieve sensitive information from other pages.
