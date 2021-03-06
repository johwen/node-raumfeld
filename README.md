# node-raumfeld

This is a node module for Raumfeld. It maps upnp commands to usage-friendly method calls.

Installation
------------

Install for node.js `npm`:

``` bash
$ npm install node-raumfeld
```

Example
-------
``` javascript
var RaumfeldManager = require('node-raumfeld');

var manager = new RaumfeldManager();

// starts discovering devices asynchronously
manager.discover();

// fetch a device and do something with it. Method calls on a device return a promise object
manager.on("rendererFound", function(renderer) {
    renderer.getVolume().then(function(value) {
        console.log(renderer.name + " volume is " + value);
    });
});

```
