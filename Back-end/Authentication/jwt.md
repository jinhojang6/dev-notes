## JWT
JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret or a public/private key pair.

References
- https://jwt.io/
- https://blog.logrocket.com/jwt-authentication-best-practices/
- https://hasura.io/blog/best-practices-of-using-jwt-with-graphql/
- https://en.wikipedia.org/wiki/JSON_Web_Token
- https://dzone.com/articles/what-is-jwt-token

<br/>

## Structure

```
const token = base64urlEncoding(header) + '.' + base64urlEncoding(payload) + '.' + base64urlEncoding(signature)
>> eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJsb2dnZWRJbkFzIjoiYWRtaW4iLCJpYXQiOjE0MjI3Nzk2Mzh9.gzSraSYS8EXBxLN_oWnFSRgCzcmJmMjLiuyu5CSpyHI
```

- Header: Identifies which algorithm is used to generate the signature

- Payload: Contains a set of claims. The JWT specification defines seven Registered Claim Names which are the standard fields commonly included in tokens.

- Signature: Securely validates the token. The signature is calculated by encoding the header and payload using Base64url Encoding and concatenating the two together with a period separator. That string is then run through the cryptographic algorithm specified in the header, in this case HMAC-SHA256. The Base64url Encoding is similar to base64, but uses different non-alphanumeric characters and omits padding.

<br/>

## Types of Token

Access token: It contains all the information the server needs to know if the user / device can access the resource you are requesting or not. They are usually expired tokens with a short validity period.

Refresh token: The refresh token is used to generate a new access token. Typically, if the access token has an expiration date, once it expires, the user would have to authenticate again to obtain an access token. With refresh token, this step can be skipped and with a request to the API get a new access token that allows the user to continue accessing the application resources.

It may also be necessary to generate a new access token when you want to access a resource that has not been accessed before, although this depends on the restrictions on API implementation.

The refresh token requires greater security when it is stored than the access token, as if it were stolen by third parties, they could use it to obtain access tokens and access the protected resources of the application. In order to cut a scenario like this one, a system must be implemented in the server to invalidate a refresh token, besides setting a lifetime that obviously must be longer than that of the access tokens.

- Reference: [Refresh token with JWT authentication in Node.js](https://solidgeargroup.com/en/refresh-token-with-jwt-authentication-node-js/#:~:text=Refresh%20token%3A%20The%20refresh%20token,to%20obtain%20an%20access%20token.)
