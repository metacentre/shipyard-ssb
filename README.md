# shipyard-ssb

List of standard ssb plugins loaded by [ssb-server](https://github.com/ssbc/ssb-server/blob/main/bin.js#L44). Used with **shipyard** to start a server configured the same as ssb-server.

# Usage

Pass the list of standard ssb plugins to shipyard to load.

```js
const shipyard = require('@metacentre/shipyard')
const ssbPlugins = require('@metacentre/shipyard-ssb')

const sbot = shipyard({}, { plugins: ssbPlugins })
```

Now you have a standard ssb-server running. You can add other plugins too; see [@metacentre/shipyard](https://github.com/metacentre/shipyard) for details.
