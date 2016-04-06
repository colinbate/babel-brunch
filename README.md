babel6-brunch
=============

*This is a fork of the official Babel plugin for brunch, one which adds .babelrc
reading and fixes patterns and sourcemaps*.

Brunch plugin using [babel](https://github.com/babel/babel) to turn ES6 code
into vanilla ES5 with no runtime required.

All the `.js` files in your project will be run through the babel compiler,
except those it is configured to ignore, unless you use the `pattern` option.

Installation
------------

`npm install --save babel6-brunch`

Configuration
-------------

This plugin will read in your `.babelrc` file or the `babel` section of your
`package.json` as the base for your configuration. These values will be
overridden by anything in the brunch config file.

Set [babel options](https://babeljs.io/docs/usage/options) in your brunch
config (such as `brunch-config.coffee`) except for `filename` and `sourceMaps`
which are handled internally.

This plugin uses, by default, the
[es2015](http://babeljs.io/docs/plugins/preset-es2015/) preset. To use no
preset, then set the configuration option to an empty array.

Additionally, you can set an `ignore` value to specify which `.js` files in
your project should not be compiled by babel. By default, `ignore` is set to
`/^(bower_components|node_modules|vendor)/`.

You can also set `pattern` to a regular expression that will match the file
paths you want compiled by babel, which will override the standard behavior of
compiling every `.js` file.

```coffee
plugins:
  babel:
    presets: ['es2015']
    ignore: [
      /^(bower_components|vendor)/
      'app/legacyES5Code/**/*'
    ]
    pattern: /\.(es6|jsx)$/
```

Change Log
----------
[See release notes page on GitHub](https://github.com/babel/babel-brunch/releases)

License
-------
[ISC](https://raw.github.com/babel/babel-brunch/master/LICENSE)
