---
source: https://github.com/Explosion-Scratch/OnDrop/blob/5088a77ba8335e78af74b2a13bb35e412bd61726/public/cookies.js#L4-L19
---

# Set a cookie based on a name and value

Set a cookie with JavaScript

```js
/**
 * Set a cookie with a value and an expiration date.
 * @param {String} name - The name of the cookie.
 * @param {String} value - The value of the cookie.
 * @param {Integer} days - The number of days until the cookie expires.
 * @returns None
 */
function setCookie(name, value, days) {
  var expires = "";
  if (days) {
    var date = new Date();
    date.setTime(date.getTime() + days * 24 * 60 * 60 * 1000);
    expires = "; expires=" + date.toUTCString();
  }
  document.cookie = name + "=" + (value || "") + expires + "; path=/";
}
```
