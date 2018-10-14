7zip-min
========

Minimal cross-platform pack/unpack with **7-zip**.   
It does not require **7zip** to be installed in your system. 
This package includes standalone **7za** version of **7-Zip** (uses precompiled binaries from [7zip-bin](https://github.com/develar/7zip-bin) package).


Supporting archive formats
--------------------------

According to [Command Line Version User's Guide](https://sevenzip.osdn.jp/chm/cmdline/index.htm) page, 7za supports only **7z**, **lzma**, **cab**, **zip**, **gzip**, **bzip2**, **Z** and **tar** formats. 


Supporting platforms
--------------------

- win (32/64)
- mac
- linux
    - arm
    - arm64
    - ia32
    - x64

To get more details check [7zip-bin](https://github.com/develar/7zip-bin) package repo. 


Usage
-----

You may use `pack` and `unpack` methods for simple packing/unpacking.

Or use `cmd` to run 7za with custom parameters (see [Command Line Version User's Guide](https://sevenzip.osdn.jp/chm/cmdline/index.htm))

```js
const _7z = require('7zip-min');

// unpack
_7z.unpack('path/to/archive.7z', 'where/to/unpack', err => {
    // done
});

// pack
_7z.pack('path/to/dir/or/file', 'path/to/archive.7z', err => {
    // done
});

// cmd
// in the first parameter you have to provide array of parameters
// check 7z's Command Line Version User's Guide - https://sevenzip.osdn.jp/chm/cmdline/index.htm
// the bellow command is equal to `7za path/to/archive.7z path/to/dir/or/file` and will add `path/to/dir/or/file` to `path/to/archive.7z` archive
_7z.cmd(['a', 'path/to/archive.7z', 'path/to/dir/or/file'], err => {
    // done
});
```

Test
----

`npm test`
