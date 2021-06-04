# shipyard-ssb

List of standard ssb plugins loaded by [ssb-server](https://github.com/ssbc/ssb-server/blob/main/bin.js#L44). Used with **shipyard** to start a server configured the same as ssb-server.

# Usage

Pass the list of standard ssb plugins to shipyard to load.

```js
const shipyard = require('@metacentre/shipyard')
const ssbPlugins = require('@metacentre/shipyard-ssb')

const sbot = shipyard(
  {},
  {
    plugins: ssbPlugins,
    lenient: ssbPlugins
  }
)
```

Now you have a standard ssb-server running. You can add other plugins too; see [@metacentre/shipyard](https://github.com/metacentre/shipyard) for details.

## Force loading of plugins with lenient list

You must also pass the list of plugins you want to be lenient with when loading. Otherwise some plugins will not load. Why? Shipyard checks the shape of plugins to ensure they are:

```js
{
  name: '',
  version: '',
  manifest: {},
  init: () =>
}
```

However some plugins such as `ssb-unix-socket` are not of the standard shape. Some are missing the manifest because they don't add methods to the RPC. Some are not even objects; they're functions. These ssb-server plugins are well established and work well so we don't want to skip loading them, so instead we pass the list of plugins to be lenient when loading them.
