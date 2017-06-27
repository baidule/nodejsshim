# nodejsshim -  Node.js Shims for Qt Script in xTuple ERP

This repo contains javascript code to emulate a Node.js environment in Qt Script.
To do this, Node.js globals and builtins are recreated by wrapping Qt objects.
For example, Node.js's `http.request` function is emulated by wrapping
`QNetworkRequest`. The Qt object used must be exposed to the Qt Script
environment. xTuple does that in the [`scriptapi`](https://github.com/xtuple/qt-client/tree/4_10_x/scriptapi)
directory of the `qt-client`.

TODO: Not all of Node.js's globals and builtins are supported at this time.

This repo also includes useful and common NPM packages like `lodash` and other
Qt object wrapped code to emulate NPM packages like `ws`.

## Installation
This xTuple Extension Package can be installed with the xTuple Updater by
installing the `nodejsshim.gz` file in the `packages` directory. It can also
be installed in a Linux environment by running the following:

```
cd /path/to/web/enabled/build/sources
ls # should show xtuple
git clone git@github.com:xtuple/nodejsshim.git
cd xtuple
scripts/build_app.js -d database-name-here -e ../nodejsshim

```

## Usage
After installation, an extension named `nodejsshim` will exist in your xTuple
database. Some example usage tests are available in
**System > Design > Node.js Shim > Examples...**
Your user must have the `MaintainScripts` privilege to run them.

To use the Node.js shim in other Qt Script code, just include this at the top
of your script file:
```
include('nodejsshim');
```
See the `nodejsshim` script for how the Node.js shim is instantiated in the
Qt Script environment. You are free to recreate that as needed for your script.

## Development

To build nodejsshim, you need Node.js 4.4.2 and Browserify installed.

#### Development Setup:
* Run `npm install`

### Development Building:
* Run `npm run build` to bundle up all the Node.js/NPM files needed for the the nodejsshim Qt Client extension package.
* Run `npm run build-release-package` to create the `packages/nodejsshim.gz` nodejsshim Qt Client extension package file.

## Maintenance note:

To update the version number of this extension you must edit the following files:

* package.json
* foundation-database/manifest.js
* foundation-database/package.sql
* foundation-database/package.xml
