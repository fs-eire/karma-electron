# karma-electron-launcher [![Build status](https://travis-ci.org/twolfson/karma-electron-launcher.svg?branch=master)](https://travis-ci.org/twolfson/karma-electron-launcher) [![Build status](https://ci.appveyor.com/api/projects/status/urgpvcip7kl9q2ih?svg=true)](https://ci.appveyor.com/project/twolfson/karma-electron-launcher)

TODO: Document

- ELECTRON_BIN
- `--show` flag
- `appDataDir` argument
- `flags` argument

[Karma][] launcher for [Electron][]

This was written to allow for directly testing in [Electron][] where we might want `require` to work automatically

[Karma]: https://github.com/karma-runner/karma
[Electron]: https://github.com/atom/electron

**Features:**

- Tested via CI on Linux and Windows
- Support for Node.js integration in the renderer process (e.g. `process`, `require`, `__filename`)
- Support for hidden browser windows
- Support for isolated test runs to prevent cookie/localStorage pollution

## Getting Started
On a project that has been set up with `karma init` already, install the module via:

```bash
# Install our module and `electron-prebuilt`
npm install karma-electron-launcher electron-prebuilt
```

Then, configure the module:

```js
// Inside `karma.conf.js`
browsers: ['Electron']

// If you would like Node integration support (e.g. `require`)
//   then, you must include this as the first file in `files`:
files: [
    require.resolve('karma-electron-launcher/lib/node-integration-iframe.js'),
    // Tests go here (e.g. 'test/*.js')
]
```

Then, we can run Karma:

```bash
karma start
```

> The `require.resolve` in `files` is necessary due to Karma using an `iframe` and Electron's `nodeIntegration` only applying to the top level window. This file implements the missing `nodeIntegration` capabilities.

## Documentation
_(Coming soon)_

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint via `npm run lint` and test via `npm test`.

## Donating
Support this project and [others by twolfson][gratipay] via [gratipay][].

[![Support via Gratipay][gratipay-badge]][gratipay]

[gratipay-badge]: https://cdn.rawgit.com/gratipay/gratipay-badge/2.x.x/dist/gratipay.svg
[gratipay]: https://www.gratipay.com/twolfson/

## Unlicense
As of Mar 03 2016, Todd Wolfson has released this repository and its contents to the public domain.

It has been released under the [UNLICENSE][].

[UNLICENSE]: UNLICENSE
