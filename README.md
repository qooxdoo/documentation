# Versioned Qooxdoo documentation

This repository contains Qooxdoo's documentation in a versioned
format. 

Whenever a tag is pushed onto the [main framework
repository](https://github.com/qooxdoo/qooxdoo), the content of the `docs`
folder of that tag's source tree is deployed to the [`gh-pages` branch of this
repository](https://github.com/qooxdoo/documentation/tree/gh-pages) in a folder
named after the tag and published at `https://qooxdoo.org/documentation/<tag>`.

Tags of the form `x.y.z` are shortened to `x.y` so that patch releases do
not create separate folders. Instead, the folder of the last feature release 
will be overwritten. 
