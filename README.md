# npmdoc-cpx

#### api documentation for  [cpx (v1.5.0)](https://github.com/mysticatea/cpx)  [![npm package](https://img.shields.io/npm/v/npmdoc-cpx.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-cpx) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-cpx.svg)](https://travis-ci.org/npmdoc/node-npmdoc-cpx)

#### Copy file globs, watching for changes.

[![NPM](https://nodei.co/npm/cpx.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/cpx)

- [https://npmdoc.github.io/node-npmdoc-cpx/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-cpx/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-cpx/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-cpx/build/apidoc.html)

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
            "name": "mysticatea"
        }
    ],
    "name": "cpx",
    "optionalDependencies": {},
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



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
