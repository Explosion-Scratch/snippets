---
source: https://github.com/Explosion-Scratch/screen-recorder/blob/23b3122774194b0926930bd4326d9562a94b7392/src/App.svelte#L588-L599
---

# Read Blob or File object as an ArrayBuffer

Use the FileReader API to read a blob as an arrayBuffer.

```js
/**
 * Use the FileReader API to read a blob as an arrayBuffer.
 * @param {Blob} blob The blob to read
 * @returns {Promise.<ArrayBuffer>} The array buffer
 */
function readAsArrayBuffer(blob) {
  return new Promise((resolve, reject) => {
    const reader = new FileReader();
    reader.readAsArrayBuffer(blob);
    reader.onloadend = () => {
      resolve(reader.result);
    };
    reader.onerror = (ev) => {
      reject(ev.error);
    };
  });
}
```
