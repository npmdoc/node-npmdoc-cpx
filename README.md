# api documentation for  [cpx (v1.5.0)](https://github.com/mysticatea/cpx)  [![npm package](https://img.shields.io/npm/v/npmdoc-cpx.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-cpx) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-cpx.svg)](https://travis-ci.org/npmdoc/node-npmdoc-cpx)
#### Copy file globs, watching for changes.

[![NPM](https://nodei.co/npm/cpx.png?downloads=true)](https://www.npmjs.com/package/cpx)

[![apidoc](https://npmdoc.github.io/node-npmdoc-cpx/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-cpx_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-cpx/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-cpx/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-cpx/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Toru Nagashima"
    },
    "bin": {
        "cpx": "bin/index.js"
    },
    "bugs": {
        "url": "https://github.com/mysticatea/cpx/issues"
    },
    "dependencies": {
        "babel-runtime": "^6.9.2",
        "chokidar": "^1.6.0",
        "duplexer": "^0.1.1",
        "glob": "^7.0.5",
        "glob2base": "^0.0.12",
        "minimatch": "^3.0.2",
        "mkdirp": "^0.5.1",
        "resolve": "^1.1.7",
        "safe-buffer": "^5.0.1",
        "shell-quote": "^1.6.1",
        "subarg": "^1.0.0"
    },
    "description": "Copy file globs, watching for changes.",
    "devDependencies": {
        "babel-cli": "^6.11.4",
        "babel-plugin-transform-runtime": "^6.9.0",
        "babel-plugin-unassert": "^2.1.1",
        "babel-preset-es2015": "^6.9.0",
        "babel-preset-power-assert": "^1.0.0",
        "babel-register": "^6.9.0",
        "codecov": "^1.0.1",
        "cross-env": "^2.0.0",
        "eslint": "^3.4.0",
        "eslint-config-mysticatea": "^6.0.0",
        "if-node-version": "^1.0.0",
        "mocha": "^3.0.2",
        "npm-run-all": "^3.1.0",
        "nyc": "^8.1.0",
        "opener": "^1.4.1",
        "power-assert": "^1.4.1",
        "rimraf": "^2.5.3",
        "shelljs": "^0.7.0",
        "through": "^2.3.8"
    },
    "directories": {},
    "dist": {
        "shasum": "185be018511d87270dedccc293171e37655ab88f",
        "tarball": "https://registry.npmjs.org/cpx/-/cpx-1.5.0.tgz"
    },
    "files": [
        "bin",
        "lib"
    ],
    "gitHead": "4e8b1931e9674de39aa9f3213f9ca410b9279fad",
    "homepage": "https://github.com/mysticatea/cpx",
    "keywords": [
        "cp",
        "cli",
        "tool",
        "commandline",
        "sync",
        "rsync",
        "watch",
        "observe",
        "copy",
        "dir",
        "directory",
        "directories",
        "file",
        "files"
    ],
    "license": "MIT",
    "main": "lib/index.js",
    "maintainers": [
        {
            "name": "mysticatea",
            "email": "star.ctor@gmail.com"
        }
    ],
    "name": "cpx",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/mysticatea/cpx.git"
    },
    "scripts": {
        "build": "cross-env NODE_ENV=production babel src --out-dir .",
        "clean": "rimraf .nyc_output bin coverage lib test-ws",
        "codecov": "nyc report -r lcovonly && codecov",
        "lint": "if-node-version \">=4\" eslint src",
        "open-coverage": "nyc report -r lcov && opener coverage/lcov-report/index.html",
        "postversion": "git push && git push --tags",
        "prebuild": "npm run clean",
        "pretest": "run-s clean lint",
        "preversion": "run-s test build",
        "prewatch": "run-s clean lint",
        "test": "cross-env NODE_ENV=development nyc --require babel-register mocha test/*.js --timeout 60000",
        "watch": "cross-env NODE_ENV=development mocha test/*.js --compilers js:babel-register --timeout 60000 --watch --growl"
    },
    "version": "1.5.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module cpx](#apidoc.module.cpx)
1.  [function <span class="apidocSignatureSpan">cpx.</span>Cpx (source, outDir, options)](#apidoc.element.cpx.Cpx)
1.  [function <span class="apidocSignatureSpan">cpx.</span>copy (source, outDir)](#apidoc.element.cpx.copy)
1.  [function <span class="apidocSignatureSpan">cpx.</span>copySync (source, outDir)](#apidoc.element.cpx.copySync)
1.  [function <span class="apidocSignatureSpan">cpx.</span>watch (source, outDir)](#apidoc.element.cpx.watch)



# <a name="apidoc.module.cpx"></a>[module cpx](#apidoc.module.cpx)

#### <a name="apidoc.element.cpx.Cpx"></a>[function <span class="apidocSignatureSpan">cpx.</span>Cpx (source, outDir, options)](#apidoc.element.cpx.Cpx)
- description and source-code
```javascript
function Cpx(source, outDir, options) {
    (0, _classCallCheck3.default)(this, Cpx);

    options = options || {}; // eslint-disable-line no-param-reassign

    var _this = (0, _possibleConstructorReturn3.default)(this, (0, _getPrototypeOf2.default)(Cpx).call(this));

    _this[SOURCE] = normalizePath(source);
    _this[OUT_DIR] = normalizePath(outDir);
    _this[DEREFERENCE] = Boolean(options.dereference);
    _this[INCLUDE_EMPTY_DIRS] = Boolean(options.includeEmptyDirs);
    _this[INITIAL_COPY] = options.initialCopy === undefined || Boolean(options.initialCopy);
    _this[PRESERVE] = Boolean(options.preserve);
    _this[TRANSFORM] = [].concat(options.transform).filter(Boolean);
    _this[UPDATE] = Boolean(options.update);
    _this[QUEUE] = new Queue();
    _this[BASE_DIR] = null;
    _this[WATCHER] = null;
    return _this;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.cpx.copy"></a>[function <span class="apidocSignatureSpan">cpx.</span>copy (source, outDir)](#apidoc.element.cpx.copy)
- description and source-code
```javascript
function copy(source, outDir) {
    var options = arguments.length <= 2 || arguments[2] === undefined ? null : arguments[2];
    var cb = arguments.length <= 3 || arguments[3] === undefined ? null : arguments[3];

    if (typeof options === "function") {
<span class="apidocCodeCommentSpan">        /* eslint-disable no-param-reassign */
</span>        cb = options;
        options = null;
        /* eslint-enable no-param-reassign */
    }

    var cpx = new Cpx(source, outDir, options);
    if (options && options.clean) {
        cpx.clean(function (err) {
            if (err == null) {
                cpx.copy(cb);
            } else if (cb != null) {
                cb(err);
            }
        });
    } else {
        cpx.copy(cb);
    }

    return cpx;
}
```
- example usage
```shell
...
'''js
var cpx = require("cpx");
'''

### cpx.copy

'''ts
cpx.copy(source, dest, options, callback)
cpx.copy(source, dest, callback)
'''

- **source** '{string}' -- A file glob of copy targets.
- **dest** '{string}' -- A file path of a destination directory.
- **options** '{object}'
- **options.clean** '{boolean}' -- The flag to remove files that copied on past before copy. Default: 'false'.
...
```

#### <a name="apidoc.element.cpx.copySync"></a>[function <span class="apidocSignatureSpan">cpx.</span>copySync (source, outDir)](#apidoc.element.cpx.copySync)
- description and source-code
```javascript
function copySync(source, outDir) {
    var options = arguments.length <= 2 || arguments[2] === undefined ? null : arguments[2];

    var cpx = new Cpx(source, outDir, options);
    if (options && options.clean) {
        cpx.cleanSync();
    }
    cpx.copySync();
}
```
- example usage
```shell
...
- **callback** '{(err: Error|null) => void}' -- A function that is called at done.

Copy files that matches with 'source' glob to 'dest' directory.

### cpx.copySync

'''ts
cpx.copySync(source, dest, options)
cpx.copySync(source, dest)
'''

A synchronous function of 'cpx.copy'.

Arguments is almost same as 'cpx.copy'.
But 'options.transform' is not supported.
...
```

#### <a name="apidoc.element.cpx.watch"></a>[function <span class="apidocSignatureSpan">cpx.</span>watch (source, outDir)](#apidoc.element.cpx.watch)
- description and source-code
```javascript
function watch(source, outDir) {
    var options = arguments.length <= 2 || arguments[2] === undefined ? null : arguments[2];

    var cpx = new Cpx(source, outDir, options);
    if (options && options.clean) {
        cpx.clean(function (err) {
            if (err == null) {
                cpx.watch();
            } else {
                cpx.emit("watch-error", err);
            }
        });
    } else {
        cpx.watch();
    }

    return cpx;
}
```
- example usage
```shell
...

- **source** '{string}' -- A file glob of copy targets.
- **dest** '{string}' -- A file path of a destination directory.
- **options** '{object}'
  - **options.clean** '{boolean}' -- The flag to remove files that copied on past before copy. Default: 'false'.
  - **options.dereference** '{boolean}' -- The flag to follow symbolic links when copying from them. Default: 'false'.
  - **options.includeEmptyDirs** '{boolean}' -- The flag to copy empty directories which is matched with the glob. Default: 'false
'.
  - **options.initialCopy** '{boolean}' -- The flag to not copy at the initial time of watch. This is for 'cpx.watch()'. Default
: 'true'.
  - **options.preserve** '{boolean}' -- The flag to copy uid, gid, atime, and mtime of files. Default: 'false'.
  - **options.transform** '{((filepath: string) => stream.Transform)[]}' -- Functions that creates a 'stream.Transform' object to
 transform each copying file.
  - **options.update** '{boolean}' -- The flag to not overwrite files on destination if the source file is older. Default: 'false
'.
- **callback** '{(err: Error|null) => void}' -- A function that is called at done.

Copy files that matches with 'source' glob to 'dest' directory.
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
