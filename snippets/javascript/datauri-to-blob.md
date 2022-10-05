---
source: https://github.com/Explosion-Scratch/OnDrop/blob/5088a77ba8335e78af74b2a13bb35e412bd61726/public/main.js#L258-L271
---

# Convert a data url to blob

Convert a base 64 encoded data url to a blob object

```js
/**
 * Converts a data URI to a Blob.
 * @param dataURI - The data URI to convert to a Blob
 * @returns The URL of the blob.
 */
function dataURItoBlob(dataURI) {
  var mime = dataURI.split(",")[0].split(":")[1].split(";")[0];
  var binary = atob(dataURI.split(",")[1]);
  var array = [];
  for (var i = 0; i < binary.length; i++) {
    array.push(binary.charCodeAt(i));
  }
  return URL.createObjectURL(new Blob([new Uint8Array(array)], { type: mime }));
}
```
