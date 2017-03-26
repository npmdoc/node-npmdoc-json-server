# api documentation for  [json-server (v0.9.6)](https://github.com/typicode/json-server)  [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-json-server.svg)](https://travis-ci.org/npmdoc/node-npmdoc-json-server)
#### Serves JSON files through REST routes.

[![NPM](https://nodei.co/npm/json-server.png?downloads=true)](https://www.npmjs.com/package/json-server)

[![apidoc](https://npmdoc.github.io/node-npmdoc-json-server/build/screen-capture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-json-server_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-json-server/build..beta..travis-ci.org/apidoc.html)

![package-listing](https://npmdoc.github.io/node-npmdoc-json-server/build/screen-capture.npmPackageListing.svg)



# package.json

```json

{
    "author": {
        "name": "Typicode",
        "email": "typicode@gmail.com"
    },
    "bin": {
        "json-server": "./bin/index.js"
    },
    "bugs": {
        "url": "https://github.com/typicode/json-server/issues"
    },
    "dependencies": {
        "body-parser": "^1.15.2",
        "chalk": "^1.1.3",
        "compression": "^1.6.0",
        "connect-pause": "^0.1.0",
        "cors": "^2.3.0",
        "errorhandler": "^1.2.0",
        "express": "^4.9.5",
        "json-parse-helpfulerror": "^1.0.3",
        "lodash": "^4.11.2",
        "lodash-id": "^0.13.0",
        "lowdb": "^0.15.0",
        "method-override": "^2.1.2",
        "morgan": "^1.3.1",
        "object-assign": "^4.0.1",
        "pluralize": "^3.0.0",
        "request": "^2.72.0",
        "server-destroy": "^1.0.1",
        "shortid": "^2.2.6",
        "update-notifier": "^1.0.2",
        "yargs": "^6.0.0"
    },
    "description": "Serves JSON files through REST routes.",
    "devDependencies": {
        "babel-cli": "^6.10.1",
        "babel-preset-es2015": "^6.16.0",
        "babel-register": "^6.16.3",
        "cross-env": "^2.0.1",
        "husky": "^0.13.0",
        "markdown-toc": "^0.13.0",
        "mkdirp": "^0.5.1",
        "mocha": "^3.1.2",
        "os-tmpdir": "^1.0.1",
        "pkg-ok": "^1.0.1",
        "rimraf": "^2.5.2",
        "server-ready": "^0.3.1",
        "standard": "^8.3.0",
        "supertest": "^2.0.0",
        "temp-write": "^2.1.0"
    },
    "directories": {
        "test": "test"
    },
    "dist": {
        "shasum": "0d6894876c5fb2a5d25ca4139dab673ab536984f",
        "tarball": "https://registry.npmjs.org/json-server/-/json-server-0.9.6.tgz"
    },
    "engines": {
        "node": ">= 0.12"
    },
    "gitHead": "c7b38279c34fdd9c9fa4b98d04d396bf196e15f6",
    "homepage": "https://github.com/typicode/json-server",
    "keywords": [
        "JSON",
        "server",
        "fake",
        "REST",
        "API",
        "prototyping",
        "mock",
        "mocking",
        "test",
        "testing",
        "rest",
        "data",
        "dummy",
        "sandbox"
    ],
    "license": "MIT",
    "main": "./lib/server/index.js",
    "maintainers": [
        {
            "name": "typicode",
            "email": "typicode@gmail.com"
        }
    ],
    "name": "json-server",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git://github.com/typicode/json-server.git"
    },
    "scripts": {
        "build": "babel src -d lib --copy-files",
        "prepublish": "npm run build && pkg-ok",
        "prepush": "npm t",
        "start": "babel-node src/cli/bin",
        "test": "npm run test:cli && npm run test:server && standard",
        "test:cli": "npm run build && cross-env NODE_ENV=test mocha test/cli/*.js",
        "test:server": "cross-env NODE_ENV=test mocha test/server/*.js",
        "toc": "markdown-toc -i README.md"
    },
    "standard": {
        "fix": true,
        "env": {
            "mocha": true
        }
    },
    "version": "0.9.6"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module json-server](#apidoc.module.json-server)
1.  [function <span class="apidocSignatureSpan">json-server.</span>create ()](#apidoc.element.json-server.create)
1.  [function <span class="apidocSignatureSpan">json-server.</span>defaults (opts)](#apidoc.element.json-server.defaults)
1.  [function <span class="apidocSignatureSpan">json-server.</span>rewriter (routes)](#apidoc.element.json-server.rewriter)
1.  [function <span class="apidocSignatureSpan">json-server.</span>router (source)](#apidoc.element.json-server.router)
1.  object <span class="apidocSignatureSpan">json-server.</span>bodyParser

#### [module json-server.bodyParser](#apidoc.module.json-server.bodyParser)
1.  [function <span class="apidocSignatureSpan">json-server.bodyParser.</span>0 (req, res, next)](#apidoc.element.json-server.bodyParser.0)
1.  [function <span class="apidocSignatureSpan">json-server.bodyParser.</span>1 (req, res, next)](#apidoc.element.json-server.bodyParser.1)



# <a name="apidoc.module.json-server"></a>[module json-server](#apidoc.module.json-server)

#### <a name="apidoc.element.json-server.create"></a>[function <span class="apidocSignatureSpan">json-server.</span>create ()](#apidoc.element.json-server.create)
- description and source-code
```javascript
function create() {
  return express().set('json spaces', 2);
}
```
- example usage
```shell
...
'''sh
$ npm install json-server --save-dev
'''

'''js
// server.js
var jsonServer = require('json-server')
var server = jsonServer.create()
var router = jsonServer.router('db.json')
var middlewares = jsonServer.defaults()

server.use(middlewares)
server.use(router)
server.listen(3000, function () {
console.log('JSON Server is running')
...
```

#### <a name="apidoc.element.json-server.defaults"></a>[function <span class="apidocSignatureSpan">json-server.</span>defaults (opts)](#apidoc.element.json-server.defaults)
- description and source-code
```javascript
defaults = function (opts) {
  var userDir = path.join(process.cwd(), 'public');
  var defaultDir = path.join(__dirname, 'public');
  var staticDir = fs.existsSync(userDir) ? userDir : defaultDir;

  opts = objectAssign({ logger: true, static: staticDir }, opts);

  var arr = [];

  // Compress all requests
  if (!opts.noGzip) {
    arr.push(compression());
  }

  // Logger
  if (opts.logger) {
    arr.push(logger('dev', {
      skip: function skip(req) {
        return process.env.NODE_ENV === 'test' || req.path === '/favicon.ico';
      }
    }));
  }

  // Enable CORS for all the requests, including static files
  if (!opts.noCors) {
    arr.push(cors({ origin: true, credentials: true }));
  }

  if (process.env.NODE_ENV === 'development') {
    // only use in development
    arr.push(errorhandler());
  }

  // Serve static files
  arr.push(express.static(opts.static));

  // No cache for IE
  // https://support.microsoft.com/en-us/kb/234067
  arr.push(function (req, res, next) {
    res.header('Cache-Control', 'no-cache');
    res.header('Pragma', 'no-cache');
    res.header('Expires', '-1');
    next();
  });

  // Read-only
  if (opts.readOnly) {
    arr.push(function (req, res, next) {
      if (req.method === 'GET') {
        next(); // Continue
      } else {
        res.sendStatus(403); // Forbidden
      }
    });
  }

  return arr;
}
```
- example usage
```shell
...
'''

'''js
// server.js
var jsonServer = require('json-server')
var server = jsonServer.create()
var router = jsonServer.router('db.json')
var middlewares = jsonServer.defaults()

server.use(middlewares)
server.use(router)
server.listen(3000, function () {
  console.log('JSON Server is running')
})
'''
...
```

#### <a name="apidoc.element.json-server.rewriter"></a>[function <span class="apidocSignatureSpan">json-server.</span>rewriter (routes)](#apidoc.element.json-server.rewriter)
- description and source-code
```javascript
rewriter = function (routes) {
  var router = express.Router();

  router.get('/__rules', function (req, res) {
    res.json(routes);
  });

  Object.keys(routes).forEach(function (route) {
    if (route.indexOf(':') !== -1) {
      router.all(route, function (req, res, next) {
        // Rewrite target url using params
        var target = routes[route];
        for (var param in req.params) {
          target = target.replace(':' + param, req.params[param]);
        }
        req.url = target;
        req.query = updateQueryString(req.query, req.url);
        next();
      });
    } else {
      router.all(route + '*', function (req, res, next) {
        // Rewrite url by replacing prefix
        req.url = req.url.replace(route, routes[route]);
        req.query = updateQueryString(req.query, req.url);
        next();
      });
    }
  });

  return router;
}
```
- example usage
```shell
...
   body: res.locals.data
  })
}
'''

#### Rewriter example

To add rewrite rules, use 'jsonServer.rewriter()':

'''javascript
// Add this before server.use(router)
server.use(jsonServer.rewriter({
  '/api/': '/',
  '/blog/:resource/:id/show': '/:resource/:id'
}))
...
```

#### <a name="apidoc.element.json-server.router"></a>[function <span class="apidocSignatureSpan">json-server.</span>router (source)](#apidoc.element.json-server.router)
- description and source-code
```javascript
router = function (source) {
  // Create router
  var router = express.Router();

  // Add middlewares
  router.use(methodOverride());
  router.use(bodyParser);

  // Create database
  var db = void 0;
  if (_.isObject(source)) {
    db = low();
    db.setState(source);
  } else {
    db = low(source, { storage: fileAsync });
  }

  validateData(db.getState());

  // Add lodash-id methods to db
  db._.mixin(lodashId);

  // Add specific mixins
  db._.mixin(mixins);

  // Expose database
  router.db = db;

  // Expose render
  router.render = function (req, res) {
    res.jsonp(res.locals.data);
  };

  // GET /db
  router.get('/db', function (req, res) {
    res.jsonp(db.getState());
  });

  // Handle /:parent/:parentId/:resource
  router.use(nested());

  // Create routes
  db.forEach(function (value, key) {
    if (_.isPlainObject(value)) {
      router.use('/' + key, singular(db, key));
      return;
    }

    if (_.isArray(value)) {
      router.use('/' + key, plural(db, key));
      return;
    }

    var msg = 'Type of "' + key + '" (' + (typeof value === 'undefined' ? 'undefined' : _typeof(value)) + ') ' + (_.isObject(source
) ? '' : 'in ' + source) + ' is not supported. ' + 'Use objects or arrays of objects.';

    throw new Error(msg);
  }).value();

  router.use(function (req, res) {
    if (!res.locals.data) {
      res.status(404);
      res.locals.data = {};
    }

    router.render(req, res);
  });

  router.use(function (err, req, res, next) {
    console.error(err.stack);
    res.status(500).send(err.stack);
  });

  return router;
}
```
- example usage
```shell
...
$ npm install json-server --save-dev
'''

'''js
// server.js
var jsonServer = require('json-server')
var server = jsonServer.create()
var router = jsonServer.router('db.json')
var middlewares = jsonServer.defaults()

server.use(middlewares)
server.use(router)
server.listen(3000, function () {
  console.log('JSON Server is running')
})
...
```



# <a name="apidoc.module.json-server.bodyParser"></a>[module json-server.bodyParser](#apidoc.module.json-server.bodyParser)

#### <a name="apidoc.element.json-server.bodyParser.0"></a>[function <span class="apidocSignatureSpan">json-server.bodyParser.</span>0 (req, res, next)](#apidoc.element.json-server.bodyParser.0)
- description and source-code
```javascript
function jsonParser(req, res, next) {
  if (req._body) {
    debug('body already parsed')
    next()
    return
  }

  req.body = req.body || {}

  // skip requests without bodies
  if (!typeis.hasBody(req)) {
    debug('skip empty body')
    next()
    return
  }

  debug('content-type %j', req.headers['content-type'])

  // determine if request should be parsed
  if (!shouldParse(req)) {
    debug('skip parsing')
    next()
    return
  }

  // assert charset per RFC 7159 sec 8.1
  var charset = getCharset(req) || 'utf-8'
  if (charset.substr(0, 4) !== 'utf-') {
    debug('invalid charset')
    next(createError(415, 'unsupported charset "' + charset.toUpperCase() + '"', {
      charset: charset
    }))
    return
  }

  // read
  read(req, res, next, parse, debug, {
    encoding: charset,
    inflate: inflate,
    limit: limit,
    verify: verify
  })
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.json-server.bodyParser.1"></a>[function <span class="apidocSignatureSpan">json-server.bodyParser.</span>1 (req, res, next)](#apidoc.element.json-server.bodyParser.1)
- description and source-code
```javascript
function urlencodedParser(req, res, next) {
  if (req._body) {
    debug('body already parsed')
    next()
    return
  }

  req.body = req.body || {}

  // skip requests without bodies
  if (!typeis.hasBody(req)) {
    debug('skip empty body')
    next()
    return
  }

  debug('content-type %j', req.headers['content-type'])

  // determine if request should be parsed
  if (!shouldParse(req)) {
    debug('skip parsing')
    next()
    return
  }

  // assert charset
  var charset = getCharset(req) || 'utf-8'
  if (charset !== 'utf-8') {
    debug('invalid charset')
    next(createError(415, 'unsupported charset "' + charset.toUpperCase() + '"', {
      charset: charset
    }))
    return
  }

  // read
  read(req, res, next, parse, debug, {
    debug: debug,
    encoding: charset,
    inflate: inflate,
    limit: limit,
    verify: verify
  })
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
