bouncy
======

Bouncy uses node's http parser innards to bounce http requests around to where
they need to go.

Use bouncy as a load balancer or http host router.

example
=======

bounce.js
---------

Bounce requests to :8001 along to :8000...

````javascript
var bouncy = require('../');
var net = require('net');

bouncy(function (req, proxy) {
    var stream = net.createConnection(8000);
    proxy(stream);
}).listen(8001);
````

install
=======

With [npm](http://npmjs.org), do:

    npm install bouncy

license
=======

MIT/X11