---
source: https://github.com/Explosion-Scratch/screen-recorder/blob/23b3122774194b0926930bd4326d9562a94b7392/src/App.svelte#L574-L587
tags: ["javascript"]
---

# Parse shell arguments

Useful when something expects a list of arguments, basically splits by spaces but not when they're in quotes.

```js
/**
 * Parse shell arguments to an array
 * Warning: Only handles double quotes
 * @param {String} text The command to parse
 * @example
 * parseArguments('ffmpeg -loglevel debug -i "Input file.mp4" output.mkv') // ['ffmpeg', '-loglevel', 'debug', '-i', 'Input file.mp4', 'output.mkv']
 * @returns {Array.<string>}
 */
function parseArguments(text) {
  text = text.replace(/\s+/g, " ");
  var args = [];
  // Allow double quotes to not split args.
  text.split('"').forEach(function (t, i) {
    t = t.trim();
    if (i % 2 === 1) {
      args.push(t);
    } else {
      args = args.concat(t.split(" "));
    }
  });
  return args;
}
```
