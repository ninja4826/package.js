# package.js
[![Build Status](http://img.shields.io/travis/s-a/package.js.svg)](https://travis-ci.org/s-a/package.js) 
[![Coverage Status](https://coveralls.io/repos/s-a/package.js/badge.svg)](https://coveralls.io/r/s-a/package.js) 
[![Codacy Badge](https://www.codacy.com/project/badge/aa693627f7f2424db1fa0cc2871f1aa5)](https://www.codacy.com/app/stephanahlf/package-js) 
[![NPM Version](http://img.shields.io/npm/v/package.js.svg?style=flat)](https://www.npmjs.org/package/package.js) 
[![NPM Downloads](https://img.shields.io/npm/dm/package.js.svg)](https://www.npmjs.org/package/package.js)  

[![Dependencies](https://img.shields.io/david/s-a/package.js.svg)](https://www.npmjs.org/package/package.js)
[![Development Dependencies](https://img.shields.io/david/dev/s-a/package.js.svg)](https://www.npmjs.org/package/package.js)

## Open your node apps for plugin developers
package.js scans the given ```packageDirectories``` for your installed application packages and creates an instance by ```require```ing ```index.js``` if a ```package.json``` file was found which contains expected package identifier(s). In the example case let us say ```{pandaPackage : true}```.
package.js will pass the ```packageContstructorSettings``` to the ```new``` ```require```d node module.  
This implements an easy way to distribute packages akka addons or plugins for node applications via NPM or other package distribution networks.  


## Installation
```npm install package.js --save;```  


## Usage
A detailed demo of usage can be found at the  [library tests](/test/main.js). To identify all application packages the method ```autoload``` expects a custom method called ```identify``` which will be executed for each package with the context  of the package itself. So far you have access there to the following properties: 
 - ```this.dir``` - The package directory.
 - ```this.meta``` - The package meta data fetched from its ```package.json```.  
A package is marked as identified if ```identify()``` returns ```true (boolean)```.  


## Custom Application Package 
Each package must contain a file called [```index.js```](/test-packages/package-1/index.js) (the main package library) and a [```package.json```](/test-packages/package-1/package.json) which is normaly used by NPM but with an extra field.  
[Full example package](/test-packages/package-1/)

## [Contributing](/CONTRIBUTING.md)

## [License](/LICENSE.md)
Copyright (c) 2015 Stephan Ahlf <stephan.ahlf@gmail.com>  
This software is dual licensed under MIT and GNU GENERAL PUBLIC LICENSE Version 3.  

[<img src="https://s-a.github.io/license/img/mit.svg" />](/LICENSE.md#MIT "Massachusetts Institute of Technology (MIT)") 
[<img src="https://s-a.github.io/license/img/gpl-3.0.svg" />](/LICENSE.md#GPL-3.0 "GNU GENERAL PUBLIC LICENSE Version 3")