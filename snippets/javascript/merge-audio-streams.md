---
source: https://github.com/Explosion-Scratch/screen-recorder/blob/23b3122774194b0926930bd4326d9562a94b7392/src/App.svelte#L461-L477
---

# Merge audio streams

Merges two MediaStreams into a single one by combining their audio

```js
/**
 * Merge two media streams into a single one by combining their audio
 * @param {MediaStream} stream1 The first media stream
 * @param {MediaStream} stream2 The second media stream
 * @returns {Array.<MediaStreamTrack>} An array of mediastream tracks
 */
function mergeStreams(stream1, stream2) {
  const ctx = new AudioContext();
  const source1 = ctx.createMediaStreamSource(stream1);
  const source2 = ctx.createMediaStreamSource(stream2);
  const destination = ctx.createMediaStreamDestination();

  const s1_gain = ctx.createGain();
  const s2_gain = ctx.createGain();

  s1_gain.gain.value = 0.7;
  s2_gain.gain.value = 0.7;

  source1.connect(s1_gain).connect(destination);
  source2.connect(s2_gain).connect(destination);

  return destination.stream.getTracks();
}
```
