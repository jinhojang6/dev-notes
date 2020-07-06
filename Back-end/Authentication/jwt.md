## JWT
JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties.

References
- https://jwt.io/
- https://blog.logrocket.com/jwt-authentication-best-practices/
- https://hasura.io/blog/best-practices-of-using-jwt-with-graphql/
- https://en.wikipedia.org/wiki/JSON_Web_Token

<br/>

## Structure

```
const token = base64urlEncoding(header) + '.' + base64urlEncoding(payload) + '.' + base64urlEncoding(signature)
>> eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJsb2dnZWRJbkFzIjoiYWRtaW4iLCJpYXQiOjE0MjI3Nzk2Mzh9.gzSraSYS8EXBxLN_oWnFSRgCzcmJmMjLiuyu5CSpyHI
```

- Header: Identifies which algorithm is used to generate the signature

- Payload: Contains a set of claims. The JWT specification defines seven Registered Claim Names which are the standard fields commonly included in tokens.

- Signature: Securely validates the token. The signature is calculated by encoding the header and payload using Base64url Encoding and concatenating the two together with a period separator. That string is then run through the cryptographic algorithm specified in the header, in this case HMAC-SHA256. The Base64url Encoding is similar to base64, but uses different non-alphanumeric characters and omits padding.