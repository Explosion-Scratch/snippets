---
source: https://gist.githubusercontent.com/Explosion-Scratch/735546e8bbe25b836193483853b1fba3/raw/831c56bc70e6053715dc298abbf9505ed2b97420/ripple.js
---

# Material design ripple effect

Applies the material design ripple effect to an element. When clicked a "ripple" will move outwards from the mouse.

```js
function ripple(el, opts = {}) {
  const time = opts.time || (+el.getAttribute("data-time") || 1000) * 3;
  const color = opts.color || el.getAttribute("data-color") || "currentColor";
  const opacity = opts.opacity || el.getAttribute("data-opacity") || ".3";
  const event = opts.event || el.getAttribute("data-event") || "click";
  el.style.overflow = "hidden";
  el.style.position = "relative";
  const handler = (e) => {
    if (el.disabled) return;
    var ripple_div = document.createElement("DIV");
    ripple_div.style.position = "absolute";
    ripple_div.style.background = `${color}`;
    ripple_div.style.borderRadius = "50%";
    var bx = el.getBoundingClientRect();
    var largestdemensions;
    if (bx.width > bx.height) {
      largestdemensions = bx.width * 3;
    } else {
      largestdemensions = bx.height * 3;
    }
    ripple_div.style.pointerEvents = "none";
    ripple_div.style.height = `${largestdemensions}px`;
    ripple_div.style.width = `${largestdemensions}px`;
    ripple_div.style.transform = `translate(-50%, -50%) scale(0)`;
    ripple_div.style.top = `${e.pageY - (bx.top + window.scrollY)}px`;
    ripple_div.style.left = `${e.pageX - (bx.left + window.scrollX)}px`;
    ripple_div.style.transition = `opacity ${time}ms ease, transform ${time}ms ease`;
    ripple_div.removeAttribute("data-ripple");
    ripple_div.style.opacity = opacity;
    el.appendChild(ripple_div);
    setTimeout(() => {
      ripple_div.style.transform = `translate(-50%, -50%) scale(1)`;
      ripple_div.style.opacity = "0";
      setTimeout(() => {
        ripple_div.remove();
      }, time);
    }, 1);
  };
  el.addEventListener(event, handler);
}
```
