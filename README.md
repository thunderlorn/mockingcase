# mOcKiNgCaSe [![Build Status](https://travis-ci.org/strdr4605/mockingcase.svg?branch=master)](https://travis-ci.org/strdr4605/mockingcase)

> Convert a string to mOcKiNgCaSe.

Read more on wikipedia [Studly caps](https://en.wikipedia.org/wiki/Studly_caps).

<img align="right" width="300" src="https://raw.githubusercontent.com/strdr4605/mockingcase/master/mOcKiNgsPoNgEbOb.png" alt="mocking spongebob" />

Inspired by the meme [Mocking Spongebob](https://knowyourmeme.com/memes/mocking-spongebob) and http://dannypage.github.io/spongebob.html

## Install

```
$ npm install mockingcase --save
```

## Usage

```js
const mOcKiNgCaSe = require('mockingcase');
// es6 - import mOcKiNgCaSe from 'mockingcase';
//  ts - import * as mOcKiNgCaSe from 'mockingcase';
//  ts - import mOcKiNgCaSe = require('mockingcase');

mOcKiNgCaSe('foo-bar');
//=> 'fOo-bAr'

mOcKiNgCaSe('aa', {random: false});
//=> 'aA'

mOcKiNgCaSe('aa', {random: true});
//=> 'aa'
//=> 'aA'
//=> 'Aa'
//=> 'AA'

mOcKiNgCaSe('42foo!bar');
//=> '42fOo!bAr'

mOcKiNgCaSe('aa123', {onlyLetters: true});
//=> 'aA'

mOcKiNgCaSe('a13%$a', {onlyLetters: true});
//=> 'aA'

mOcKiNgCaSe('foo bar', {firstUpper: true});
//=> 'FoO BaR'

mOcKiNgCaSe('foo', {firstUpper: true, random: true});
//=> 'Foo'
//=> 'FOo'
//=> 'FoO'
//=> 'FOO'

mOcKiNgCaSe(['foo','bar']);
//=> 'fOoBaR'

mOcKiNgCaSe(undefined);
//=> Error "An input is required"

mOcKiNgCaSe.log('foo bar');
// console.log('fOo bAr');

// Optionally create String.prototype.toMockingCase
mOcKiNgCaSe.overrideString();

'foo_bar'.toMockingCase();
//=> 'fOo_bAr'

'foo_bar'.toMockingCase({firstUpper: true});
//=> 'FoO_BaR'

// Optionally overrides console.log and returns a mOcKiNgCaSe object
mOcKiNgCaSe.overrideConsole();
console.log('Hello');
//=> 'hElLo'

const mOcKiNgCaSe = require('mockingcase').overrideConsole();
console.log('foobar')
// => 'fOoBaR'
mOcKiNgCaSe('foobar');
// => 'fOoBaR'

// Optionally create an initial config with default options
const mOcKiNgCaSe = require('mockingcase').config({onlyLetters: true, firstUpper: true});
// const mOcKiNgCaSe = mOcKiNgCaSe.config({onlyLetters: true, firstUpper: true});

mOcKiNgCaSe('foo bar42');
//=> 'FoO BaR'

mOcKiNgCaSe('foo bar42', {onlyLetters: false, firstUpper: false});
//=> 'fOo bAr42'
```

## API

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [mOcKiNgCaSe(input, [options]) ⇒ <code>string</code>](#mOcKiNgCaSe)
- [mOcKiNgCaSe.overrideString() ⇒ <code>mOcKiNgCaSe</code>](#mOcKiNgCaSe.overrideString)
- [String.prototype.toMockingCase([options]) ⇒ <code>string</code>](#String.prototype.toMockingCase)
- [mOcKiNgCaSe.config(defaultOptions) ⇒ <code>mOcKiNgCaSe</code>](#mOcKiNgCaSe.config)
- [mOcKiNgCaSe.log(input, [options])](#mOcKiNgCaSe.log)
- [mOcKiNgCaSe.overrideConsole([options]) ⇒ <code>mOcKiNgCaSe</code>](#mOcKiNgCaSe.overrideConsole)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

<a name="mOcKiNgCaSe"></a>

### mOcKiNgCaSe(input, [options]) ⇒ <code>string</code>
Converts the input string(s) to mOcKiNgCaSe.

**Kind**: global function
**Returns**: <code>string</code> - string in mOcKiNgCaSe

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| input | <code>string</code> \| <code>string[]</code> |  | String(s) to be converted |
| [options] | <code>object</code> | <code>{random: false, onlyLetters: false, firstUpper: false}</code> | Conversion options |
| options.random | <code>boolean</code> | <code>false</code> | If case conversion should be randomized |
| options.onlyLetters | <code>boolean</code> | <code>false</code> | If non letters characters should be removed |
| options.firstUpper | <code>boolean</code> | <code>false</code> | If the first letter should be capitalized instead of the second when converting to mOcKiNgCaSe (e.g. MoCkInGcAsE). When combined with `options.random`, the first letter of the random string will be capitalized |

<hr>

<a name="mOcKiNgCaSe.overrideString"></a>

### mOcKiNgCaSe.overrideString() ⇒ <code>mOcKiNgCaSe</code>
Creates `String.prototype.toMockingCase()`.

**Kind**: global function
**Returns**: <code>mOcKiNgCaSe</code> - The mOcKiNgCaSe module.
**See**: <code>toMockingCase</code>

<hr>

<a name="String.prototype.toMockingCase"></a>

### String.prototype.toMockingCase([options]) ⇒ <code>string</code>
Converts `this` string to mOcKiNgCaSe.

**NOTE**: this function is created by invoking `mOcKiNgCaSe.overrideString()`.

**Kind**: prototype
**Returns**: <code>string</code> - local string in mOcKiNgCaSe

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| [options] | <code>object</code> | <code>{random: false, onlyLetters: false, firstUpper: false}</code> | Conversion options |
| options.random | <code>boolean</code> | <code>false</code> | If case conversion should be randomized |
| options.onlyLetters | <code>boolean</code> | <code>false</code> | If non letters characters should be removed |
| options.firstUpper | <code>boolean</code> | <code>false</code> | If the first letter should be capitalized instead of the second when converting to mOcKiNgCaSe (e.g. MoCkInGcAsE). When combined with `options.random`, the first letter of the random string will be capitalized |

<hr>

<a name="mOcKiNgCaSe.config"></a>

### mOcKiNgCaSe.config(defaultOptions) ⇒ <code>mOcKiNgCaSe</code>
Outputs a mOcKiNgCaSe with default options.

**Kind**: static method of [<code>mOcKiNgCaSe</code>](#mOcKiNgCaSe)
**Returns**: mOcKiNgCaSe with default options

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| defaultOptions | <code>object</code> |  | Options for converting |
| defaultOptions.random | <code>boolean</code> | <code>false</code> | If case conversion should be randomized |
| defaultOptions.onlyLetters | <code>boolean</code> | <code>false</code> | If non letters characters should be removed |
| defaultOptions.firstUpper | <code>boolean</code> | <code>false</code> | If the first letter should be capitalized instead of the second when converting to mOcKiNgCaSe (e.g. MoCkInGcAsE). When combined with `options.random`, the first letter of the random string will be capitalized |

<hr>

<a name="mOcKiNgCaSe.log"></a>

### mOcKiNgCaSe.log(input, [options])
Outputs a message to the console in mOcKiNgCaSe.

**Kind**: static method of [<code>mOcKiNgCaSe</code>](#mOcKiNgCaSe)

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| input | <code>string</code> \| <code>string[]</code> |  | String(S) to be converted |
| [options] | <code>object</code> | <code>{random: false, onlyLetters: false, firstUpper: false}</code> | Conversion options |
| options.random | <code>boolean</code> | <code>false</code> | If case conversion should be randomized |
| options.onlyLetters | <code>boolean</code> | <code>false</code> | If non letters characters should be removed |
| options.firstUpper | <code>boolean</code> | <code>false</code> | If the first letter should be capitalized instead of the second when converting to mOcKiNgCaSe (e.g. MoCkInGcAsE). When combined with `options.random`, the first letter of the random string will be capitalized |

<a name="mOcKiNgCaSe"></a>

<hr>

<a name="mOcKiNgCaSe.overrideConsole"></a>

### mOcKiNgCaSe.overrideConsole([options]) ⇒ <code>mOcKiNgCaSe</code>
Overrides the console.log input annd prints it in the mOcKiNgCaSe.

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| [options] | <code>object</code> | <code>{random: false, onlyLetters: false, firstUpper: false}</code> | Conversion options |
| options.random | <code>boolean</code> | <code>false</code> | If case conversion should be randomized |
| options.onlyLetters | <code>boolean</code> | <code>false</code> | If non letters characters should be removed |
| options.firstUpper | <code>boolean</code> | <code>false</code> | If the first letter should be capitalized instead of the second when converting to mOcKiNgCaSe (e.g. MoCkInGcAsE). When combined with `options.random`, the first letter of the random string will be capitalized |

<a name="mOcKiNgCaSe"></a>

<hr>

**See also [Mockingcase bindings for ReasonML](https://redex.github.io/package/unpublished/strdr4605/bs-mockingcase)**
