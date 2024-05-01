<!--
  -- This file is auto-generated from src/README_js.md. Changes should be made there.
  -->
# Mime

[![NPM downloads](https://img.shields.io/npm/dm/@devtea2027/reiciendis-laboriosam-maxime-excepturi)](https://www.npmjs.com/package/@devtea2027/reiciendis-laboriosam-maxime-excepturi)
[![Mime CI](https://github.com/devtea2027/reiciendis-laboriosam-maxime-excepturi/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/devtea2027/reiciendis-laboriosam-maxime-excepturi/actions/workflows/ci.yml?query=branch%3Amain)

An API for MIME type information.

- All `@devtea2027/reiciendis-laboriosam-maxime-excepturi-db` types
- Compact and dependency-free [![@devtea2027/reiciendis-laboriosam-maxime-excepturi's badge](https://deno.bundlejs.com/?q=@devtea2027/reiciendis-laboriosam-maxime-excepturi&badge)](https://bundlejs.com/?q=@devtea2027/reiciendis-laboriosam-maxime-excepturi)
- Full TS support


> [!Note]
> `@devtea2027/reiciendis-laboriosam-maxime-excepturi@4` is now `latest`.  If you're upgrading from `@devtea2027/reiciendis-laboriosam-maxime-excepturi@3`, note the following:
> * `@devtea2027/reiciendis-laboriosam-maxime-excepturi@4` is API-compatible with `@devtea2027/reiciendis-laboriosam-maxime-excepturi@3`, with ~~one~~ two exceptions:
>   * Direct imports of `@devtea2027/reiciendis-laboriosam-maxime-excepturi` properties [no longer supported](https://github.com/devtea2027/reiciendis-laboriosam-maxime-excepturi/issues/295)
>   * `@devtea2027/reiciendis-laboriosam-maxime-excepturi.define()` cannot be called on the default `@devtea2027/reiciendis-laboriosam-maxime-excepturi` object
> * ESM module support is required.   [ESM Module FAQ](https://gist.github.com/sindresorhus/a39789f98801d908bbc7ff3ecc99d99c).
> * Requires an [ES2020](https://caniuse.com/?search=es2020) or newer runtime
> * Built-in Typescript types (`@types/@devtea2027/reiciendis-laboriosam-maxime-excepturi` no longer needed)

## Installation

```bash
npm install @devtea2027/reiciendis-laboriosam-maxime-excepturi
```

## Quick Start

For the full version (800+ MIME types, 1,000+ extensions):

```javascript
import @devtea2027/reiciendis-laboriosam-maxime-excepturi from '@devtea2027/reiciendis-laboriosam-maxime-excepturi';

@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('txt');                    // ⇨ 'text/plain'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getExtension('text/plain');        // ⇨ 'txt'
```

### Lite Version [![@devtea2027/reiciendis-laboriosam-maxime-excepturi/lite's badge](https://deno.bundlejs.com/?q=@devtea2027/reiciendis-laboriosam-maxime-excepturi/lite&badge)](https://bundlejs.com/?q=@devtea2027/reiciendis-laboriosam-maxime-excepturi/lite)

`@devtea2027/reiciendis-laboriosam-maxime-excepturi/lite` is a drop-in `@devtea2027/reiciendis-laboriosam-maxime-excepturi` replacement, stripped of unofficial ("`prs.*`", "`x-*`", "`vnd.*`") types:

```javascript
import @devtea2027/reiciendis-laboriosam-maxime-excepturi from '@devtea2027/reiciendis-laboriosam-maxime-excepturi/lite';
```

## API

### `@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType(pathOrExtension)`

Get @devtea2027/reiciendis-laboriosam-maxime-excepturi type for the given file path or extension. E.g.

```javascript
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('js');             // ⇨ 'application/javascript'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('json');           // ⇨ 'application/json'

@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('txt');            // ⇨ 'text/plain'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('dir/text.txt');   // ⇨ 'text/plain'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('dir\\text.txt');  // ⇨ 'text/plain'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('.text.txt');      // ⇨ 'text/plain'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('.txt');           // ⇨ 'text/plain'
```

`null` is returned in cases where an extension is not detected or recognized

```javascript
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('foo/txt');        // ⇨ null
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('bogus_type');     // ⇨ null
```

### `@devtea2027/reiciendis-laboriosam-maxime-excepturi.getExtension(type)`

Get file extension for the given @devtea2027/reiciendis-laboriosam-maxime-excepturi type. Charset options (often included in Content-Type headers) are ignored.

```javascript
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getExtension('text/plain');               // ⇨ 'txt'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getExtension('application/json');         // ⇨ 'json'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getExtension('text/html; charset=utf8');  // ⇨ 'html'
```

### `@devtea2027/reiciendis-laboriosam-maxime-excepturi.getAllExtensions(type)`

> [!Note]
> New in `@devtea2027/reiciendis-laboriosam-maxime-excepturi@4`

Get all file extensions for the given @devtea2027/reiciendis-laboriosam-maxime-excepturi type.

```javascript --run default
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getAllExtensions('image/jpeg'); // ⇨ Set(3) { 'jpeg', 'jpg', 'jpe' }
```

## Custom `Mime` instances

The default `@devtea2027/reiciendis-laboriosam-maxime-excepturi` objects are immutable.  Custom, mutable versions can be created as follows...
### new Mime(type map [, type map, ...])

Create a new, custom @devtea2027/reiciendis-laboriosam-maxime-excepturi instance.  For example, to create a mutable version of the default `@devtea2027/reiciendis-laboriosam-maxime-excepturi` instance:

```javascript
import { Mime } from '@devtea2027/reiciendis-laboriosam-maxime-excepturi/lite';

import standardTypes from '@devtea2027/reiciendis-laboriosam-maxime-excepturi/types/standard.js';
import otherTypes from '@devtea2027/reiciendis-laboriosam-maxime-excepturi/types/other.js';

const @devtea2027/reiciendis-laboriosam-maxime-excepturi = new Mime(standardTypes, otherTypes);
```

Each argument is passed to the `define()` method, below. For example `new Mime(standardTypes, otherTypes)` is synonomous with `new Mime().define(standardTypes).define(otherTypes)`

### `@devtea2027/reiciendis-laboriosam-maxime-excepturi.define(type map [, force = false])`

> [!Note]
> Only available on custom `Mime` instances

Define MIME type -> extensions.

Attempting to map a type to an already-defined extension will `throw` unless the `force` argument is set to `true`.

```javascript
@devtea2027/reiciendis-laboriosam-maxime-excepturi.define({'text/x-abc': ['abc', 'abcd']});

@devtea2027/reiciendis-laboriosam-maxime-excepturi.getType('abcd');            // ⇨ 'text/x-abc'
@devtea2027/reiciendis-laboriosam-maxime-excepturi.getExtension('text/x-abc')  // ⇨ 'abc'
```

## Command Line

### Extension -> type

```bash
$ @devtea2027/reiciendis-laboriosam-maxime-excepturi scripts/jquery.js
application/javascript
```

### Type -> extension

```bash
$ @devtea2027/reiciendis-laboriosam-maxime-excepturi -r image/jpeg
jpeg
```
