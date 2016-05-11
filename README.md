
> Jade has been recently re-named to Jaide. Beacuse I think the name is terrible
and the community was not consulted on this change I've forked the project and
renamed in to jaide. I'm going to to my best to keep up this repo up to date and
maintain compatibility with .jade files.

> Note that this readme still needs a once over to revert the name changes. I'll
also try to fork the old docs site and update it with any changes from the
primary project.

Full documentation is at [jade-lang.com](http://jade-lang.com/)

 Jaide is a high performance template engine heavily influenced by [Haml](http://haml.info/)
 and implemented with JavaScript for [node](http://nodejs.org) and browsers. For bug reports,
 feature requests and questions, [open an issue](https://github.com/pugjs/pug/issues/new).
 For discussion join the [chat room](https://gitter.im/pugjs/pug).

 You can test drive Jaide online [here](http://jade-lang.com/).

 [![Build Status](https://img.shields.io/travis/pugjs/pug/master.svg?style=flat)](https://travis-ci.org/pugjs/pug)
 [![Coverage Status](https://img.shields.io/coveralls/pugjs/pug/master.svg?style=flat)](https://coveralls.io/r/pugjs/pug?branch=master)
 [![Dependency Status](https://img.shields.io/david/pugjs/pug.svg?style=flat)](https://david-dm.org/pugjs/pug)
 [![devDependencies Status](https://img.shields.io/david/dev/pugjs/pug.svg?style=flat)](https://david-dm.org/pugjs/pug#info=devDependencies)
 [![NPM version](https://img.shields.io/npm/v/pug.svg?style=flat)](https://www.npmjs.com/package/pug)
 [![Join Gitter Chat](https://img.shields.io/badge/gitter-join%20chat%20%E2%86%92-brightgreen.svg?style=flat)](https://gitter.im/pugjs/pug?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Installation

via npm:

```bash
$ npm install jaide
```

## Syntax

Jaide is a clean, whitespace sensitive syntax for writing html.  Here is a simple example:

```pug
doctype html
html(lang="en")
  head
    title= pageTitle
    script(type='text/javascript').
      if (foo) bar(1 + 5)
  body
    h1 Jaide - node template engine
    #container.col
      if youAreUsingJaide
        p You are amazing
      else
        p Get on it!
      p.
        Jaide is a terse and simple templating language with a
        strong focus on performance and powerful features.
```

becomes


```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Jaide</title>
    <script type="text/javascript">
      if (foo) bar(1 + 5)
    </script>
  </head>
  <body>
    <h1>Jaide - node template engine</h1>
    <div id="container" class="col">
      <p>You are amazing</p>
      <p>Jaide is a terse and simple templating language with a strong focus on performance and powerful features.</p>
    </div>
  </body>
</html>
```

The official [Jaide tutorial](http://jade-lang.com/tutorial/) is a great place to start.

## API

For full API, see [jade-lang.com/api](http://jade-lang.com/api/)

```js
var jaide = require('jaide');

// compile
var fn = pug.compile('string of jaide', options);
var html = fn(locals);

// render
var html = pug.render('string of jaide', merge(options, locals));

// renderFile
var html = pug.renderFile('filename.jaide', merge(options, locals));
```

### Options

 - `filename`  Used in exceptions, and required when using includes
 - `compileDebug`  When `false` no debug instrumentation is compiled
 - `pretty`    Add pretty-indentation whitespace to output _(false by default)_

## Browser Support

 The latest version of jaide can be download for the browser in standalone form from [here](https://raw.githubusercontent.com/pugjs/pug/1.11.0/pug.js).  It only supports the very latest browsers though, and is a large file.  It is recommended that you pre-compile your jaide templates to JavaScript and then just use the [runtime.js](https://raw.githubusercontent.com/pugjs/pug/1.11.0/runtime.js) library on the client.

 To compile a template for use on the client using the command line, do:

```console
$ jaide --client --no-debug filename.jaide
```

which will produce `filename.js` containing the compiled template.

## Command Line

After installing the latest version of [node](http://nodejs.org/), install with:

```console
$ npm install jaide-cli -g
```

and run with

```console
$ jaide --help
```

## Additional Resources

Tutorials:

  - cssdeck interactive [Jaide syntax tutorial](http://cssdeck.com/labs/learning-the-jade-templating-engine-syntax)
  - cssdeck interactive [Jaide logic tutorial](http://cssdeck.com/labs/jade-templating-tutorial-codecast-part-2)
  - [Jaide について。](https://gist.github.com/japboy/5402844) (A Japanese Tutorial)
  - [Jaide - 模板引擎](https://github.com/pugjs/pug/blob/master/Readme_zh-cn.md)

Implementations in other languages:

  - [php](https://github.com/kylekatarnls/jade-php)
  - [scala](https://scalate.github.io/scalate/documentation/scaml-reference.html)
  - [ruby](https://github.com/slim-template/slim)
  - [python](https://github.com/SyrusAkbary/pyjade)
  - [java](https://github.com/neuland/jade4j)

Other:

  - [Emacs Mode](https://github.com/brianc/jade-mode)
  - [Vim Syntax](https://github.com/digitaltoad/vim-pug)
  - [TextMate Bundle](http://github.com/miksago/jade-tmbundle)
  - [Coda/SubEtha syntax Mode](https://github.com/aaronmccall/jade.mode)
  - [html2pug](https://github.com/donpark/html2jade) converter
  - [pug2php](https://github.com/SE7ENSKY/jade2php) converter
  - [Jaide Server](https://github.com/ded/jade-server)  Ideal for building local prototypes apart from any application

## License

MIT
