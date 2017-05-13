# base64-background-image

![Project is deprecated!](https://cdn.rawgit.com/OpenSourceWorkflow/generator-kickstart/master/deprecation-warning.svg)

This project has been deprecated!

scss mixin for creating svg base64 background-image width png fallback

## Options

```scss
  $url; // path to svg file without '.svg'
  $useFallback: true; // create no-svg fallback?
  $altFallback:""; // specify custom fallback image instead of <name>.png
```

## Usage Example

```scss
// fallback png has same name as svg icon
%icon {
  @include base64-background-image("icon");
}

// you want to use an alternating png as fallback
%icon2 {
  @include base64-background-image("icon2", "alternating-icon-2");
}


// extend the placeholders
.ico {
  @extend %icon;
}

.ico2 {
  @extend %icon2;
}
```

Generates

```css
/* default with same-name fallback image */
.ico {
  background-image: url('data:image/svg+xml;base64,ABC...');
  background-repeat: no-repeat;
}
.no-svg .ico {
  background-image: url('icon.png');
}

/* default with different fallback image */
.ico2 {
  background-image: url('data:image/svg+xml;base64,ABC...');
  background-repeat: no-repeat;
}
.no-svg .ico2 {
  background-image: url('alternating-icon-2.png');
}
```

## Requirements

* SVG feature detection with class: 'no-svg'
* Compass
* SASS

## Installation

```bash
bower install base64-background-image
```
