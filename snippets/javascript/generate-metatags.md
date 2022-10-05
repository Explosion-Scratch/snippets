---
source: https://gist.githubusercontent.com/Explosion-Scratch/a54287dc65586d7c6fb0e2d716942b6c/raw/039e08973e03c72fb6ac3c88f53428275f9f3eee/meta.js
---

# Generate HTML meta tags

Function to generate meta tags based on an object with title, description, url, author, keywords, site and image.

```js
/**
 * Function to generate meta tags based on an object with title, description, url, author, keywords, site and image.
 * @param {Object} meta An object containing properties about the meta tags to be generated
 * @param {String} meta.title The title of the site
 * @param {String} meta.author The author of the site
 * @param {String} meta.keywords The keyword array, joined by a comma
 * @param {String} meta.description A description of the site/page
 * @param {String} meta.color A hex code for the theme color of the site
 * @param {String} meta.url The URL of the site
 * @param {String} meta.image A path to the image for the site
 */
const generate = (meta) => {
  return [
    { charset: "utf-8" },
    { lang: "en" },
    { name: "viewport", content: "width=device-width, initial-scale=1" },
    { name: "format-detection", content: "telephone=no" },
    { name: "title", content: meta.title },
    { name: "author", content: meta.author },
    {
      name: "keywords",
      content: meta.keywords || "",
    },
    { name: "robots", content: "index,follow" },
    { name: "language", content: "English" },
    { name: "description", content: meta.description },
    { name: "theme-color", content: meta.color },
    { name: "og:type", content: "website" },
    { name: "apple-mobile-web-app-title", content: meta.title },
    { name: "og_site_name", content: meta.site || meta.title },
    { name: "og:site_name", content: meta.site || meta.title },
    { name: "og:locale", content: "en_US" },
    { name: "og:url", content: meta.url },
    { name: "og:title", content: meta.title },
    { name: "og:description", content: meta.description },
    { name: "og:image", content: meta.image },
    { name: "twitter:card", content: "summary_large_image" },
    { name: "twitter:url", content: meta.url },
    { name: "twitter:title", content: meta.title },
    { name: "twitter:description", content: meta.description },
    { name: "twitter:image", content: meta.image },
  ]
    .map((i) => {
      var out = { ...i };
      if (!out.hid) {
        out.hid = out.name;
      }
      return out;
    })
    .map(
      (i) =>
        `<meta name=${JSON.stringify(i.name)} content=${JSON.stringify(
          i.content
        )}/>`
    )
    .join("\n");
};
```
