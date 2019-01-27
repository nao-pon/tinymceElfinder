# tinymceElfinder

elFinder integrator for TinyMCE 4 and 5.

tinymceElfinder provides the functions of `file_picker_callback` and `images_upload_handler` through the [eFinder](https://github.com/Studio-42/elFinder).

## Requires

- TinyMCE 4.x or 5.x
- jQuery and jQueryUI
- elFinder >= 2.1.47 or latest nightly
- Modem browsers compatible with ES6

## Getting Started

### Load required JavaScripts

```html
<!-- jQuery and jQuery-UI -->
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jqueryui/1.12.1/jquery-ui.min.js"></script>
<link rel="stylesheet" type="text/css" href="https://cdnjs.cloudflare.com/ajax/libs/jqueryui/1.12.1/themes/smoothness/jquery-ui.min.css"/>
<!-- elFinder (load latest nightly) -->
<script type="text/javascript" src="https://studio-42.github.io/elFinder/demo/js/elfinder.min.js"></script>
<!-- tinyMCE -->
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/tinymce/4.9.2/tinymce.min.js"></script>
<!-- tinymceElfinder -->
<script type="text/javascript" src="https://nao-pon.github.io/tinymceElfinder/tinymceElfinder.js"></script>
```

### Make tinymceElfinder instance

```javascript
const mceElf = new tinymceElfinder({
    // connector URL (Set your connector)
    url: 'php/connector.minimal.php',
    // upload target folder hash for this tinyMCE
    uploadTargetHash: 'l1_lw', // Hash value on elFinder of writable folder
    // elFinder dialog node id
    nodeId: 'elfinder' // Any ID you decide
});
```

Note: Options passed to tinymceElfinder also have the option of elFinder.

### TinyMCE initialization

```javascript
tinymce.init({
    plugins: "image, link, media, imagetools",
    file_picker_callback : mceElf.browser,
    images_upload_handler: mceElf.uploadHandler
});
```

## Live DEMO

- https://nao-pon.github.io/tinymceElfinder/
