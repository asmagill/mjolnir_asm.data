mjolnir._asm.data
=================

Functions for data encoding and decoding data within Mjolnir.  This module contains a variety
of modules that were separated in Hydra, but seemed too small/somewhat related enough that
combining them seemed reasonable.

This module is based primarily on code from the previous incarnation of Mjolnir by [Steven Degutis](https://github.com/sdegutis/).

### Luarocks Install
~~~bash
$ luarocks [--tree=mjolnir] install mjolnir._asm.data
~~~

### Local Install
~~~bash
$ git clone https://github.com/asmagill/mjolnir_asm.data
$ cd mjolnir_asm.data
$ [PREFIX=/usr/local] make install
~~~

### Require

~~~lua
data = require("mjolnir._asm.data")
~~~

### Functions

~~~lua
data.hexdump(string [, count]) -> string
~~~
Treats the input string as a binary blob and returns a prettied up hex dump of it's contents. By default, a newline character is inserted after every 16 bytes, though this can be changed by also providing the optional count argument.

~~~lua
data.pasteboard.changecount() -> number
~~~
The number of times the pasteboard owner changed
(useful to see if the pasteboard was updated, by seeing if the value of this function changes).

~~~lua
data.pasteboard.getcontents() -> string
~~~
Returns the contents of the pasteboard as a string, or nil if it can't be done

~~~lua
data.pasteboard.setcontents(string) -> boolean
~~~
Sets the contents of the pasteboard to the string value passed in.  Returns success status as true or false.

~~~lua
data.userdata_tostring(userdata) -> string
~~~
Returns the userdata object as a binary string.

~~~lua
data.utf8.chars(str) -> {str, ...}
~~~
Splits the string into groups of (UTF-8 encoded) strings representing what humans would consider individual characters.

The result is a sequential table, such that table.concat(result) produces the original string.

~~~lua
data.utf8.count(str) -> int
~~~
Returns the number of characters as humans would count them.

~~~lua
data.uuid() -> string
~~~
Returns a newly generated UUID as a string

### Variables

~~~lua
data.applekeys[...]
~~~
Array of symbols representing special keys in the mac environment, as per http://macbiblioblog.blogspot.com/2005/05/special-key-symbols.html.

### License

> Released under MIT license.
>
> Copyright (c) 2014 Aaron Magill
>
> Permission is hereby granted, free of charge, to any person obtaining a copy
> of this software and associated documentation files (the "Software"), to deal
> in the Software without restriction, including without limitation the rights
> to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
> copies of the Software, and to permit persons to whom the Software is
> furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in
> all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
> IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
> FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
> AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
> LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
> OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
> THE SOFTWARE.
