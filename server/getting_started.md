# Getting Started with Qooxdoo Server

## Installation

See [Requirements](requirements.md) for details on how to obtain and install
Qooxdoo Server

## Basic Example

The following example shows how to use the _Qooxdoo Server_ package in a node
environment, having installed the package via npm.

On the basic level, you can just load the Server module into your own program,
using your runtime's loading primitives. Here is a simple example for Node.js:


```
var qx = require('@Qooxdoo/framework')

// create anmial class
qx.Class.define("my.Animal", {
  extend : qx.core.Object,
  properties : {
    legs : {init: 4}
  }
});

// create dog class
qx.Class.define("my.Dog", {
  extend : my.Animal,
  members : {
    bark : function() {
      console.log("ARF! I have " + this.getLegs() + " legs!");
    }
  }
});

var dog = new my.Dog();
dog.bark();
```

Only two lines in this example are specific to the server environment: The first
one, where you include the Qooxdoo package and the implementation of the `bark`
function, which uses node's `console` object. To run the example in Rhino,
simply change the first line to something like this:

```
load(["path/to/qooxdoo.js"]);
```

and replace `console.log` with `print`.

The rest of the code is plain Qooxdoo-style JavaScript which can be run in a
browser, too. For more information on that topic, take a look at the
documentation about [Object Orientation](../core/oo_introduction.md) .

## Additional Scenarios

The _Qooxdoo Server_ package does not contain any server-dependent code so it
can also be used in a browser e.g. to have the features described above without
the need to use the rest of Qooxdoo. Another interesting scenario might be to
use the package in a
[web worker](https://developer.mozilla.org/en/Using_web_workers) , which is also
a DOM-less environment.
