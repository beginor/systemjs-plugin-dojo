# Dojo loader plugin for SystemJS

## Installation

First install this plugin with npm:

```sh
npm install systemjs-plugin-dojo
```

Then add map to the loader:

```js
SystemJS.config({
    map: {
        'dojo-loader': 'node_modules/systemjs-plugin-dojo/dojo.js'
    }
});
```

## Setup

First make sure dojo or esri works through `dojoConfig`, for example:

```js
(function (global) {
    'use strict';
    global.dojoConfig = {
        async: true,
        baseUrl: '.',
        packages: [
            { name: 'dgrid', location: 'bower_components/dgrid' },
            { name: 'dijit', location: 'bower_components/dijit' },
            { name: 'dojo', location: 'bower_components/dojo' },
            { name: 'dojox', location: 'bower_components/dojox' },
            { name: 'dstore', location: 'bower_components/dstore' },
            { name: 'moment', location: 'bower_components/moment' },
            { name: 'esri', location: 'bower_components/esri' }
        ]
    };
})(window);
```

And link dojo in your html file:

```html
<script src="dojoConfig.js"></script>
<script src="bower_components/dojo/dojo.js"></script>
```

Then config all dojo related package load with the loader, for example:

```js
SystemJS.config({
    meta: {
        'dojo/*': { loader: 'dojo-loader' },
        'esri/*': { loader: 'dojo-loader' }
    }
});
```

## License

[MIT](LICENSE)

## Thanks to

[roemhildtg](https://gist.github.com/roemhildtg/4dce79f9bffe74b99a6a6cea3f44604f)
[tomwayson](https://github.com/tomwayson)
