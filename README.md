CSS Media Query Parser
===============

[![Build Status](https://travis-ci.org/cvrebert/css-mq-parser.png?branch=master)](https://travis-ci.org/cvrebert/css-mq-parser)
[![devDependency Status](https://img.shields.io/david/dev/cvrebert/css-mq-parser.svg)](https://david-dm.org/cvrebert/css-mq-parser#info=devDependencies)
[![npm Version](https://badge.fury.io/js/css-mq-parser.png)](https://npmjs.org/package/css-mq-parser)

Parses CSS media query expressions.

Installation
------------

Install via npm:

```shell
$ npm install css-mq-parser
```

Usage
-----

This package has one export: `parse()`, which can parse CSS media
query expressions.

### Parsing

Existing CSS Parsers don't do a great job at parsing the details of media
queries. That's where `css-mq-parser` shines. You can parse a media query
expression and get an AST back by using the `parse()` method.

```javascript
var mediaQuery = require('css-mq-parser'),
    ast        = mediaQuery.parse('screen and (min-width: 48em)');
```

The `ast` variable will have the following payload:

```javascript
[
    {
        inverse: false,
        type   : 'screen',

        expressions: [
            {
                modifier: 'min',
                feature : 'width',
                value   : '48em'
            }
        ]
    }
]
```


License & Acknowledgements
-------

This project is a fork of [css-mediaquery](https://www.npmjs.com/package/css-mediaquery).
This software is free to use under the Yahoo! Inc. BSD license.
See the [LICENSE file](https://github.com/cvrebert/css-mq-parser/blob/master/LICENSE.txt) for license text and copyright information.
