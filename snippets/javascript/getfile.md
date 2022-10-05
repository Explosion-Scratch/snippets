---
source: https://github.com/Explosion-Scratch/OnDrop/blob/5088a77ba8335e78af74b2a13bb35e412bd61726/public/main.js#L276-L288
---

# Get file

Open the choose file picker then get a File object from it.

```js
/**
 * Open the file picker and ask for a file.
 * @returns {Promise.<File>} The file object.
 */
async function getFile() {
  return new Promise((resolve) => {
    var e = document.createElement("input");
    e.style.display = "none";
    e.type = "file";
    document.body.appendChild(e);
    e.onchange = (event) => {
      resolve(e.files[0]);
      e.remove();
    };
    e.click();
  });
}
```
