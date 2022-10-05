---
source: https://github.com/Explosion-Scratch/OnDrop/blob/5088a77ba8335e78af74b2a13bb35e412bd61726/public/cookies.js#L35-L42
---

# Erase a cookie

Erase a cookie by setting its expiration date to 1970-01-01T00:00:01Z.

```js
/**
 * Erase a cookie by setting its expiration date to 1970-01-01T00:00:01Z.
 * @param name - The name of the cookie.
 * @returns None
 */
function eraseCookie(name) {
  document.cookie = name + "=; Path=/; Expires=Thu, 01 Jan 1970 00:00:01 GMT;";
}
```
