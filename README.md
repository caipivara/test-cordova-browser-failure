# test-cordova-browser-failure
Example to show when `cordova requirements` crash with browser plugin.

https://github.com/apache/cordova-browser/issues/65

# Environtment
- CLJ: `8.1.2`
- cordova-browser: `5.0.4`

# Trace

The issue:

```
$ cordova create test-cordova-browser com.example.hello "HelloWorld"
$ cordova platform add browser@5.0.4
$ cordova requirements -d
```

Throws:

```
$ cordova requirements -d

Checking opts.platforms  :
PlatformApi successfully found for platform browser

Requirements check results for browser:
Cannot read property 'forEach' of undefined
TypeError: Cannot read property 'forEach' of undefined
    at /usr/local/lib/node_modules/cordova/src/cli.js:406:35
    at Array.map (<anonymous>)
    at /usr/local/lib/node_modules/cordova/src/cli.js:397:68
    at _fulfilled (/usr/local/lib/node_modules/cordova/node_modules/q/q.js:854:54)
    at /usr/local/lib/node_modules/cordova/node_modules/q/q.js:883:30
    at Promise.promise.promiseDispatch (/usr/local/lib/node_modules/cordova/node_modules/q/q.js:816:13)
    at /usr/local/lib/node_modules/cordova/node_modules/q/q.js:624:44
    at runSingle (/usr/local/lib/node_modules/cordova/node_modules/q/q.js:137:13)
    at flush (/usr/local/lib/node_modules/cordova/node_modules/q/q.js:125:13)
    at process._tickCallback (internal/process/next_tick.js:61:11)
```
