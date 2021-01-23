# Qooxdoo Release Notes

Starting with Qooxdoo 6.0.0, there are lots of changes which have happened "under the hood"
which mean great things for the project, a better development environment for coders, and
still maintaining that rock solid reliability, scalability and no compromise on backwards
compatibility and coding standards.


## Compiler
There is a whole new compiler and command line tool (the `qx` command), written entirely in 
Javascript and replacing the Python toolchain (which is still supported but is officially 
deprecated).

The compiler (the `qx compile` command) is fast, and continuously compiles code written to 
the latest ES6 language specs into ES5, giving you ultimate compatibility without compromising
ease of coding.

Documentation is at [https://qooxdoo.org/documentation/#/development/cli/commands](https://qooxdoo.org/documentation/#/development/cli/commands)


## Packages
The new compiler supports "packages" (which are analogous to the old "contrib" system), where
it is able to detect and install widgets and libraries written by anyone and made available on 
GitHub.  This is similar to how `npm` or other package managers work, using GitHub as the
database to pull from.

See the `qx package` command for more information on how to incorporate packages into your
application.

Documentation is at [https://qooxdoo.org/documentation/#/development/cli/packages](https://qooxdoo.org/documentation/#/development/cli/packages).
All published packages are cataloged and showcased in our online [Package Browser](https://qooxdoo.org/qxl.packagebrowser/qxl.packagebrowser/#), 
which is itself a packaged application that can be locally installed.


## Automatic Memory Management
A big improvement is that it is no longer necessary to manually `.dispose()` most objects when you
no longer need them; this isn't true for objects such as widgets, but for most objects you can simply 
stop referring to the object and Javascript's garbage collection will take care of the rest.

**NOTE** this does have an issue for backwards compatibility - previously, every single object was
stored in `qx.core.ObjectRegistry` but it was this list that prevented normal garbage collection.  In
6.0.0, only widgets are added to that list automatically.  You can still add objects to the `qx.core.ObjectRegistry`
if you want to.

Although it is *mostly* widgets that are in the `ObjectRegistry`, it's actually any class which implements
the `qx.core.IDisposable` interface; if you add that interface to your own classes, they will automatically
added to the `ObjectRegistry` and you must manually call `.dispose()`.

Documentation is at [https://qooxdoo.org/documentation/#/development/howto/memory_management](https://qooxdoo.org/documentation/#/development/howto/memory_management)


## Object ID
All objects now support an ID mechanism which is heirarchial and can be navigated by code; this simplifies
development and enables external automated testing tools to find your widgets and other objects.

Documentation is at [https://qooxdoo.org/documentation/#/core/object_id](https://qooxdoo.org/documentation/#/core/object_id)


## Promises
Promises are now integrated into the framework, represented by the `qx.Promise` class.  Events and property
apply methods can return promises and will when for previous promises to complete before going onto
the next step.

Documentation is at [https://qooxdoo.org/documentation/#/core/promises](https://qooxdoo.org/documentation/#/core/promises)


## Webfonts
Qooxdoo now supports webfonts / iconfonts everywhere an image can be placed.

Documentation is [https://qooxdoo.org/documentation/#/development/howto/icon_fonts](https://qooxdoo.org/documentation/#/development/howto/icon_fonts)


## New Theme
There's a new theme based on Google Materials design philosophy and available in Light and Dark modes - the
theme is called Tangible and is `qx.theme.TangibleLight` and `qx.theme.TangibleDark`.


## Licensing and Open Source Ownership
The first big change, chronologically speaking, was that 1&1, the company which originally 
developed Qooxdoo donated the project completely into the public domain; the project is now 
entirely community based and open source, and as part of this we changed the licensing
model to the MIT license.

None of this should make any practical difference to anyone using Qooxdoo to develop their 
applications - the MIT license is at least as liberal as the Eclipse license that was used
before, and we've made sure that all contributions have formally switched to MIT.

As a team, we are a small group of experienced developers based around the world who use
Qooxdoo every day and have a vested interest in maintaining the project and keeping it strong.

All code is available at GitHub [https://github.com/qooxdoo](https://github.com/qooxdoo),
where we have published policies and rules on contributing; we actively encourage anyone to
submit Pull Requests to contribute to the project.

We chat in public on [Gitter](https://gitter.im/qooxdoo/qooxdoo) and answer questions
on [StackOverflow](https://stackoverflow.com/questions/tagged/qooxdoo)

Documentation is at [https://qooxdoo.org/documentation/#/development/contribute](https://qooxdoo.org/documentation/#/development/contribute)



