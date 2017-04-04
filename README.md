# api documentation for  babel-register (v6.24.0)  [![npm package](https://img.shields.io/npm/v/npmdoc-babel-register.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-babel-register) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-babel-register.svg)](https://travis-ci.org/npmdoc/node-npmdoc-babel-register)
#### babel require hook

[![NPM](https://nodei.co/npm/babel-register.png?downloads=true)](https://www.npmjs.com/package/babel-register)

[![apidoc](https://npmdoc.github.io/node-npmdoc-babel-register/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-babel-register_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-babel-register/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-babel-register/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-babel-register/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Sebastian McKenzie",
        "email": "sebmck@gmail.com"
    },
    "browser": "lib/browser.js",
    "dependencies": {
        "babel-core": "^6.24.0",
        "babel-runtime": "^6.22.0",
        "core-js": "^2.4.0",
        "home-or-tmp": "^2.0.0",
        "lodash": "^4.2.0",
        "mkdirp": "^0.5.1",
        "source-map-support": "^0.4.2"
    },
    "description": "babel require hook",
    "devDependencies": {
        "decache": "^4.1.0"
    },
    "directories": {},
    "dist": {
        "shasum": "5e89f8463ba9970356d02eb07dabe3308b080cfd",
        "tarball": "https://registry.npmjs.org/babel-register/-/babel-register-6.24.0.tgz"
    },
    "license": "MIT",
    "main": "lib/node.js",
    "maintainers": [
        {
            "name": "amasad",
            "email": "amjad.masad@gmail.com"
        },
        {
            "name": "hzoo",
            "email": "hi@henryzoo.com"
        },
        {
            "name": "jmm",
            "email": "npm-public@jessemccarthy.net"
        },
        {
            "name": "loganfsmyth",
            "email": "loganfsmyth@gmail.com"
        },
        {
            "name": "sebmck",
            "email": "sebmck@gmail.com"
        },
        {
            "name": "thejameskyle",
            "email": "me@thejameskyle.com"
        }
    ],
    "name": "babel-register",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "https://github.com/babel/babel/tree/master/packages/babel-register"
    },
    "scripts": {},
    "version": "6.24.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module babel-register](#apidoc.module.babel-register)
1.  object <span class="apidocSignatureSpan">babel-register.</span>cache

#### [module babel-register.cache](#apidoc.module.babel-register.cache)
1.  boolean <span class="apidocSignatureSpan">babel-register.cache.</span>__esModule
1.  [function <span class="apidocSignatureSpan">babel-register.cache.</span>get ()](#apidoc.element.babel-register.cache.get)
1.  [function <span class="apidocSignatureSpan">babel-register.cache.</span>load ()](#apidoc.element.babel-register.cache.load)
1.  [function <span class="apidocSignatureSpan">babel-register.cache.</span>save ()](#apidoc.element.babel-register.cache.save)



# <a name="apidoc.module.babel-register"></a>[module babel-register](#apidoc.module.babel-register)



# <a name="apidoc.module.babel-register.cache"></a>[module babel-register.cache](#apidoc.module.babel-register.cache)

#### <a name="apidoc.element.babel-register.cache.get"></a>[function <span class="apidocSignatureSpan">babel-register.cache.</span>get ()](#apidoc.element.babel-register.cache.get)
- description and source-code
```javascript
function get() {
  return data;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.babel-register.cache.load"></a>[function <span class="apidocSignatureSpan">babel-register.cache.</span>load ()](#apidoc.element.babel-register.cache.load)
- description and source-code
```javascript
function load() {
  if (process.env.BABEL_DISABLE_CACHE) return;

  process.on("exit", save);
  process.nextTick(save);

  if (!_fs2.default.existsSync(FILENAME)) return;

  try {
    data = JSON.parse(_fs2.default.readFileSync(FILENAME));
  } catch (err) {
    return;
  }
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.babel-register.cache.save"></a>[function <span class="apidocSignatureSpan">babel-register.cache.</span>save ()](#apidoc.element.babel-register.cache.save)
- description and source-code
```javascript
function save() {
  var serialised = "{}";

  try {
    serialised = (0, _stringify2.default)(data, null, "  ");
  } catch (err) {

    if (err.message === "Invalid string length") {
      err.message = "Cache too large so it's been cleared.";
      console.error(err.stack);
    } else {
      throw err;
    }
  }

  (0, _mkdirp.sync)(_path2.default.dirname(FILENAME));
  _fs2.default.writeFileSync(FILENAME, serialised);
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
