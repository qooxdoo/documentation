# Compiler Events

When you use a [`compile.js`](../configuration/api.md) to configure the
compilation process, or if you use the compiler's [API](./API.md), in your
own code, the different object instances that you work with fire events to
which your code can listen. Here is a list of events with a brief explanation:

## Makers

`qx.tool.compiler.makers.Maker` instances fire the following events:  
- `making`: Fired when making of apps begins.
- `made`: Fired when making of apps is done. 
- `writingApplication`: Fired when writing of single application starts.
- `writingApplications`: Fired when application writing starts.
- `writtenApplication`: Fired when writing of single application is complete.
- `writtenApplications`: Fired after writing of all applications.

## Analyzer

`qx.tool.compiler.Analyser` instances fire the following events:
- `compilingClass`: Fired when a class is about to be compiled.
- `compiledClass`: Fired when a class is compiled.
- `alreadyCompiledClass`: Fired when a class is already compiled (but needed for compilation)
- `saveDatabase`: Fired when the database is been saved database

## CLI Commands

Instances of `qx.tool.cli.commands.Compile` and its subclasses fire the following events:
- `checkEnvironment`: Fired after all enviroment data is collected. 
- `compilingClass`: Fired when a class is about to be compiled.
- `compiledClass`: Fired when a class is compiled.
- `making`: Fired when making of apps begins.
- `made`: Fired when making of apps is done.
- `minifyingApplication`: Fired when minification begins.
- `minifiedApplication`: Fired when minification is done.
- `saveDatabase`: Fired when the database is been saved data.
- `writingApplication`: Fired when writing of single application starts.
- `writingApplications`: Fired when application writing starts.
- `writtenApplication`: Fired when writing of single application is complete.
- `writtenApplications`: Fired after writing of all applications.
