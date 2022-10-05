---
source: https://github.com/Explosion-Scratch/OnDrop/blob/5088a77ba8335e78af74b2a13bb35e412bd61726/public/main.js#L237-L240
---

# Get a search param from the current URL

Parse location.search and get the value of a search parmeter

```js
/**
 * Parse location.search and get the value of a search parmeter
 * @param {String} name The name of the parameter to get
 */
function param(name) {
  let params = new URLSearchParams(location.search);
  return params.get(name);
}
```
