---
title: Browser
---

The `app/browser` directory is where JavaScript files for the browser live. These JavaScript files can import other modules from your project as well as any installed packages that can run in the browser. Files in the `app/browser` directory will be bundled to the `/public/pages/` directory in your project and will be exposed the to browser at `/_public/pages/` for loading by script tags.
```javascript
<script type="module" src="/_public/pages/my-file.mjs"></script>
```

## Add a browser bundle

Create a JavaScript file for the browser.

```bash
app
├── api ............... data routes
│   └── index.mjs
└── browser ........... browser JavaScript
    └── index.mjs
```

```javascript
// Inside `app/browser/index.mjs`
const message = document.getElementById('message')
message.innerHTML = '👋 Hello from your bundle!'
```

## Source a bundle in a page

Add a script tag and load it from `/_public/pages/index.mjs`

```html
<main>
<h1>My awesome page</h1>
<p id="message"></p>
</main>
<script type="module" src="/_public/pages/index.mjs"></script>
```


<doc-callout level="info" mark="💭">

The `/_public` endpoint is created for you so that Enhance can do the tedious work of replacing your authored file name with a fingerprinted one to avoid caching issues.

</doc-callout>


## That's it

Now you can use this built-in pattern for sharing elements with the browser and progressively enhancing your pages with JavaScript.
