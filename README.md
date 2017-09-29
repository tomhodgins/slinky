# slinky

**Add JavaScript tests to &lt;link> tags to toggle stylesheets**

Similar to how you can add media queries to `<link>` tags with the `media=""` attribute, Slinky lets you define a custom `data-selector=""` and `data-test=""` attributes to any `<link>` tag to define an element to watch, and a JavaScript test to evaluate from the context of the matching element.

A simple usage might toggle the display of a stylesheet when the `#sidebar` element is wider than 500px:

```html
<link
  rel="stylesheet"
  href="sidebar.css"
  media="none"
  data-selector="#sidebar"
  data-test="this.offsetWidth > 500"
>
```

By default Slinky will add event listeners for `window.load`, `window.resize`, `window.input` and `window.click`, but you can override this by optionally specifying a `data-event=""` attribute as well. This stylesheet would listen to `window.scroll` alone:

```html
<link
  rel="stylesheet"
  href="scroll.css"
  media="none"
  data-selector="body"
  data-test="this.scrollTop > innerHeight"
  data-event="scroll"
>
```

Note that in these examples I've included `media="none"` so the stylesheets default to being hidden - for progressive enhancement it you wish to default to the stylesheets applying unless they need to be hidden by JS, you can leave the `media="none"` off and the stylesheet will load by default, instead of remain hidden by default.

## Links

- [Slinky.js website](https://tomhodgins.github.io/slinky)
- [Demo page](https://tomhodgins.github.io/slinky/tests/demo.html)
- [Slinky on Codepen](https://codepen.io/tomhodgins/pen/veZYPK)
