---
type: example
summary: Deliver an HTML page from an HTML string directly inside the Worker script.
demo: https://returning-html.workers-sites-examples.workers.dev
tags:
  - Originless
pcx-content-type: configuration
title: Return small HTML page
weight: 1
layout: example
---

```js
const html = `<!DOCTYPE html>
<body>
  <h1>Hello World</h1>
  <p>This markup was generated by a Cloudflare Worker.</p>
</body>`;

async function handleRequest(request) {
  return new Response(html, {
    headers: {
      'content-type': 'text/html;charset=UTF-8',
    },
  });
}

addEventListener('fetch', event => {
  return event.respondWith(handleRequest(event.request));
});
```
