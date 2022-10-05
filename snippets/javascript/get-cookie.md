---
source: https://github.com/Explosion-Scratch/OnDrop/blob/5088a77ba8335e78af74b2a13bb35e412bd61726/public/cookies.js#L20-L34
---

# Get a cookie

Get a cookie based on name and value

```js
/**
 * Given a cookie name, return the value of the cookie.
 * @param {String} name - The name of the cookie to retrieve.
 * @returns The value of the cookie.
 */
function getCookie(name) {
  var nameEQ = name + "=";
  var ca = document.cookie.split(";");
  for (var i = 0; i < ca.length; i++) {
    var c = ca[i];
    while (c.charAt(0) == " ") c = c.substring(1, c.length);
    if (c.indexOf(nameEQ) == 0) return c.substring(nameEQ.length, c.length);
  }
  return null;
}
```
