base64-background-image
============

scss mixin for creating svg base64 background-image width png fallback

Usage Example
-------------

```scss
// somewhere in your base
%icon {
  @include base64-background-image("icon");
}

// extend the placeholder
.ico {
  @extend %disruption-orange;
}
```

Generates

```css
.ico {
  background-image: url('data:image/svg+xml;base64,ABC...');
  background-repeat: no-repeat;
}
.no-svg .ico {
  background-image: url('icon.png');
}
```

Requirements
------------

* Compass
* SASS

Installation
------------

```bash
bower install base64-background-image
```
