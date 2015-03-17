resin-request
-------------

[![npm version](https://badge.fury.io/js/resin-request.svg)](http://badge.fury.io/js/resin-request)
[![dependencies](https://david-dm.org/resin-io/resin-request.png)](https://david-dm.org/resin-io/resin-request.png)
[![Build Status](https://travis-ci.org/resin-io/resin-request.svg?branch=master)](https://travis-ci.org/resin-io/resin-request)

Resin.io HTTP request client.

Installation
------------

Install `resin-request` by running:

```sh
$ npm install --save resin-request
```

Documentation
-------------

### resinRequest.request(Object options, Function callback[, Function onProgress])

Make an HTTP request to a resin server.

#### String options.url

The relative url to make the request to.

#### String options.remoteUrl

The absolute url of the resin server to make the request to.

#### String options.token

The session token to use.

#### String options.method

The HTTP method to perform. Defaults to `GET`.

#### StreamWritable options.pipe

A stream to pipe the request. Useful if downloading a file.

If you use this option, you may use the `onProgress` callback.

#### Function callback(error, response, body)

This function is called when the request is completed.

#### Function onProgress(state)

A function called to notify the progress if piping the request.

The `state` object contains:

- `percentage`: The percentage of the request.
- `received`: The amount of bytes received.
- `total`: The total amount of bytes.
- `eta`: The request time estimate.
- `delta`: The number of bytes received since the last call to `onProgress`.

Notice that if the resource doesn't expose a `content-length` containing the size of the resource, `state` will be undefined.

Tests
-----

Run the test suite by doing:

```sh
$ gulp test
```

Contribute
----------

- Issue Tracker: [github.com/resin-io/resin-request/issues](https://github.com/resin-io/resin-request/issues)
- Source Code: [github.com/resin-io/resin-request](https://github.com/resin-io/resin-request)

Before submitting a PR, please make sure that you include tests, and that [coffeelint](http://www.coffeelint.org/) runs without any warning:

```sh
$ gulp lint
```

Support
-------

If you're having any problem, please [raise an issue](https://github.com/resin-io/resin-request/issues/new) on GitHub.

License
-------

The project is licensed under the MIT license.