ScriptInclude
=============

ScriptInclude allows you to asynchronously load `script` tags into the browser. I made it because I wanted a `#include` statement like other languages have, so I did my best to recreate that.

ScriptInclude aims to be _tiny_ and easy to understand. There is no dependency management or anything.

It's meant to be minified and inlined, like so:

```html
<!-- ... -->
<body>
  <!-- ... -->

  <script>

  // ScriptInclude, minified and inlined
  include=function(){ /* ... */ }

  // my stuff
  include('jquery.js', function() {
    include('main.js');
  });

  </script>

  <!-- ... -->
```

Some example usage
------------------

### Include a single file ###

```javascript
include('library.js', function() {
  // library.js has been loaded, now we can use it
});
```

Callbacks are optional.

### Include multiple files ###

```javascript
include('underscore.js', 'backbone.js', function() {
  // Underscore and Backbone are loaded in, let's go for it
});
```

You can include as many files as you want.
