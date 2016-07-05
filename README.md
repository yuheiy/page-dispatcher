# Page Dispatcher

Divide methods by HTML files.

## Installation

```bash
$ npm install @yuheiy/simple-dispatcher
```

## Usage

```javascript
'use strict';

var Dispatcher = require('@yuheiy/page-dispatcher');
var dispatcher = new Dispatcher();

dispatcher.route('common', function () {
  // run on all pages
});

dispatcher.route('home', function (message) {
  // run only on home
  console.log(message);
});

window.run = dispatcher.run.bind(dispatcher);
```

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Home - Site Name</title>
  </head>

  <body>
    <h1>Home</h1>

    <script src="app.js"></script>
    <script>
      run('common');
      run('home', 'This is a home of this site.');
    </script>
  </body>
</html>
```
