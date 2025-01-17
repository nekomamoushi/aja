# Send HTTP Headers with the HttpClient

## Wrong Solution

```typescript
let headers = new HttpHeaders();
headers = headers.set("header-1", "content-1");
headers = headers.set("header-2", "content-2");
```

In that case, the headers will not be sent because the instance of the new `HttpHeader` class is an **immutable** object.
Invoking class methods will return a new instance each time.

## Proper Solution

```typescript
const headers = new HttpHeaders()
  .set("Content-Type", "application/json; charset=utf-8")
  .set("Accept-Encoding", "gzip,deflate");
```
