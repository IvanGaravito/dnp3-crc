# dnp3-crc

> A DNP 3.0 CRC checker and calculator for Node.js

## Introduction

This is a module for checking and calculating the CRC used for DNP 3.0, ported from lpdu.cpp @ dnplib.

DNP stands for Distributed Network Protocol and more info can be found at [www.dnp.org](http://www.dnp.org/)

## Installation

```sh
$ npm install dnp3-crc
```

## API

### dnp3-crc.check(block)

Checks the two octet CRC at the end of `block` and returns if it is ok. `block` is an array.

### dnp3-crc.calculate(block)

Calculates the CRC for `block` and returns it.

## Usage

```js
var crc = require('./dnp3-crc')

crc.calculate([0x05,0x64,0x05,0xC0,0x01,0x00,0x00,0x00])
//0xf891

crc.check([0x05,0x64,0x05,0xC0,0x01,0x00,0x00,0x00,0x91,0xF8])
//true

crc.check([0x05,0x64,0x0B,0xC9,0x01,0x00,0x00,0x00,0x91,0xF8])
//false
```

## License 

(The MIT License)

Copyright (c) 2014 Ivan Garavito &lt;ivangaravito@gmail.com&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.