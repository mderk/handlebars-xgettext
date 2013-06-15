# handlebars-xgettext
> Extract translatable strings from Handlebars templates.

## Installation
``` bash
$ npm install handlebars-xgettext
```

## Usage
``` bash
$ handlebars-xgettext [options] path/to/handlebars/templates translation.po
```
All files in `path/to/handlebars/templates` and its subdirectories are scanned for translatable strings in Handlebars format and written to the specified gettext PO file.
**Warning:** currently the PO file is always overwritten.

Translatable strings should be marked up like this:
``` html
<button>{{gettext "Login"}}</button>
```
By default, `_` can also be used (instead of `gettext`).

It is up to you to define the Handlebars i18n helper. Your project will need to contain something similar to:
``` javascript
Handlebars.registerHelper('_', function(key) {
  return i18n.gettext(key);
});
```

[Jed](http://slexaxton.github.com/Jed/) is a very convenient library to manage internationalization from JavaScript in the gettext way.

## Development

* Run `npm test` or `grunt` to run tests.
* Run `grunt watch` to watch for file changes and run tests.

Pull requests and issues are greatly appreciated ;-)

## Note

handlebars-xgettext initial development was founded by Dijiwan.

## License

Copyright (c) 2012 Guillaume Marty

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the "Software"), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES
OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY,
WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.
