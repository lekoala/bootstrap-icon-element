# bootstrap-icon-element

[![NPM](https://nodei.co/npm/bootstrap-icon-element.png?mini=true)](https://nodei.co/npm/bootstrap-icon-element/) 
[![Downloads](https://img.shields.io/npm/dt/bootstrap-icon-element.svg)](https://www.npmjs.com/package/bootstrap-icon-element)

## How to use

Simply include the library

```js
import BootstrapIcon from "./bootstrap-icon-element.js";
```

And call your icons! 

```html
<bs-i name="star"></bs-i>
<bs-i name="github" style="--size: 24px"></bs-i>
<bs-i name="alarm-fill" style="--size: 36px; color: red"></bs-i>

<a href="#" class="btn btn-primary"> <bs-i name="github" class="me-1"></bs-i> Github </a>
```

You need to include the following css:

```css
bs-i {
    --size: 1em;
    display: inline-flex;
    width: var(--size);
    height: var(--size);
    vertical-align: middle;
}
bs-i svg {
    display: block;
    width: 100%;
    height: 100%;
}
```

You can set a custom base path:

```html
<script>
    window.BootstrapIcon = { path: "/icons" };
</script>
```

## Why a custom element

- External sprite or font is loading all the icons which lead to extra load time
- Including svg is leading to really super long html and not very developer friendly
- No need for custom js inliner, it feels cleaner overall

## Why external css

A custom element css is not loaded until the component itself is loaded, which
can lead to FOUC and things moving around as the icon appear.
The solution I've found so far is to apply some global css rules than are known
before the component is loaded.

## Demo

https://codepen.io/lekoalabe/pen/WNpQPBm

## Need some other icon set ?

Check my other custom element: https://github.com/lekoala/last-icon
