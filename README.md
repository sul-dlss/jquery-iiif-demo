jQuery IIIF Demo
================

A jQuery plugin to create interactive IIIF demo

## Installation

Include script *after* the jQuery library:

```html
<script src="/path/to/jquery.iiif-demo.js"></script>
```

## Usage Example

Create session cookie:

```javascript
$('.demo').iiifDemo({
  selectOptions: {
    '0,1200,5000,200': {
      'w,'      : [0],
      'w - 200,': [0],
      'w - 400,': [0]
    },
    'full': {
      ',h'      : [0, 90, 180, 270],
      ',h - 200': [0, 90, 180, 270]
    },
    '2000,1000,800,800': {
      '400,400': [0, 90, 180, 270],
      '200,200': [0, 90, 180, 270],
      '100,100': [0, 90, 180, 270]
    }
  },
  iiifImgInfo: {
    baseUrl: 'http://example.iiif.server/image/iiif/abcd123',
    region: 'full',
    size: 'full',
    rotation: 0,
    quality: 'native',
    format: 'jpg'
  }
});
```
Here, `w` and `h` will be substituted with image container's dimensions to calculate select options.

Expected HTML structure for the plugin to work with -

```html
<div class="demo">
  ...
  <select name="" class="iiif-select-region"></select>
  <select name="" class="iiif-select-size"></select>
  <select name="" class="iiif-select-rotation"></select>
  ...
  <div class="iiif-image-container">
    <img src="">
  </div>
</div>

```
