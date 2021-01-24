# Qooxdoo Roadmap

With the release of Qooxdoo v6.0.0, the project is looking forward to removing a number of deprecated features and adding new components and modules that will broaden our feature set and build on the solid foundation that Qooxdoo currently is.

Below is a summary of our plans for v7 and a rough outline of what we're thinking about for v8; if there is anything you feel strongly about on either list (or you think that there is something missing) please feel free to talk to us about it - after all, if you don't us what you think, we'll never know!


## v7.0.0:

* **Remove deprecated python tool chain** (the "generator"); this requires reworking the test runner framework, which although it is written in Javascript as a Qooxdoo application, the collection and compilation of unit tests depends on the generator.

* **Allow new JavaScript syntax** With the generator gone, which only understood ECMAScript 5, framework code can use any new JavaScript syntax that is supported by the compiler (internally powered by the Babel transpiler). 

* **Remove other deprecated code**

* **Qooxdoo CMS** - currently a pre-alpha work in progress, the CMS sub project will bring a complete server and client development system with pluggable CMS.  Repo is [qooxdoo/qxl.cms](https://github.com/qooxdoo/qxl.cms)

* **JSX** - adding support for JSX will enable super-lightweight user interfaces and DOM manipulation, from the server and the client.  Available in [PR#9967]https://github.com/qooxdoo/qooxdoo/pull/9967

* **Qooxdoo Thin Client** - when building a normal website (for example, the kind of website which might be backed by a CMS) there are lots of times when a full blown Qooxdoo app would not be appropriate, eg a login form or a simple data capture form.  The Qooxdoo Thin Client builds on the JSX feature to give easy access to DOM to build simple user interface components from the server as well as the client, based on Google Materials design.

* **Qooxdoo Remote Objects and Persistence** - another two incubators which are required for the Qooxdoo CMS, these add seamless remote control of Qooxdoo objects (think "RPC" but for entire objects, where property changes on the client can be reflected on the server) and persistently storing objects to disk.  Repos are [qooxdoo/incubator.qx.io.remote](https://github.com/qooxdoo/incubator.qx.io.remote) and [qooxdoo/incubator.qx.io.persistence](https://github.com/qooxdoo/incubator.qx.io.persistence)

* **Qooxdoo RPC** - provides a framework for transport-agnostic higher-level i/o protocols to the qx.io namespace; although this is already stable and ready for production use, it's due to be integrated into the core framework.  Repo is [qooxdoo/incubator.qx.io.jsonrpc](https://github.com/qooxdoo/incubator.qx.io.jsonrpc)

## v8.0.0

Please remember that this list is a rough plan and subject to change.

* **Native properties** - currently, Qooxdoo properties have to be accessed via `.getPropertyValue()`, we would like to change this to be more javascript and have the same functionality also available via `.propertyValue`.  This also means mapping `qx.data.Array` accessors, so that `myArr.getItem(0)` can be rewritten as just `myArr[0]`

* **Native Classes** - the Qooxdoo class mechanism offers more features than standard ES6 classes, but it should be possible to integrate the two - for example, allow an ES6 `class` to extend from a Qooxdoo class and vice versa.

* **Native Decorators** - Qooxdoo annotations are similar to Javascript Decorators, and we would like to integrate the Qooxdoo annotations with the native syntax for decorators


## Other features

Our issue tracker contains [more features planned for the next release](https://github.com/qooxdoo/qooxdoo/milestone/66)...
