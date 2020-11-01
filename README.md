# homebridge-flair

[Flair Smart Vent](https://flair.co/products/vent) plug-in for [Homebridge](https://github.com/nfarina/homebridge) using the Flair API.


# Installation

<!-- 2. Clone (or pull) this repository from github into the same path Homebridge lives (usually `/usr/local/lib/node_modules`). Note: the code currently on GitHub is in beta, and is newer than the latest published version of this package on `npm` -->
1. Install homebridge using: `npm install -g homebridge`
2. Install this plug-in using: `npm install -g homebridge-flair`
3. Update your configuration file. See example `config.json` snippet below.

# Configuration

Configuration sample (edit `~/.homebridge/config.json`):

```json
{
    "platforms": [
        {
            "clientId": "client_id",
            "clientSecret": "client_secret",
            "username": "user",
            "password": "pass",
            "pollInterval": 60,
            "platform": "Flair",
            "ventAccessoryType": "windowCovering"
        }
    ]
}
```

# Obtaining Credentials

In order to use this plugin you will need to obtain a client id and client secret from Flair. 

Follow the instructions [here](https://documenter.getpostman.com/view/5353571/Rzfnj6YR?version=latest#intro). 

Specifically you need to:
1. Create a Flair account with a developer email address at my.flair.co.
2. Provide this email address to hello@flair.co and they will send you a set of developer credentials.

You will use the client id and secret they send you in the config block above.

# Auto Vs Manual Mode

When you use Pucks with your setup the pucks will appear in the app as a Thermostat. If you turn those thermostats off it will put the Flair system into Manual mode. If you turn the thermostat to any other setting it will set your system to Flair's Auto mode.

# Vent Accessory Type

You can specify how vent accessories are shown in HomeKit with the `ventAccessoryType` property.

`windowCovering` - Window Covering
`fan` - Fan
`airPurifier` - Air Purifier


### Commit format

Commits should be formatted as `type(scope): message`

The following types are allowed:

| Type | Description |
|---|---|
| feat | A new feature |
| fix | A bug fix |
| docs | Documentation only changes |
| style | Changes that do not affect the meaning of the code (white-space, formatting,missing semi-colons, etc) |
| refactor | A code change that neither fixes a bug nor adds a feature |
| perf | A code change that improves performance |
| test | Adding missing or correcting existing tests |
| chore | Changes to the build process or auxiliary tools and libraries such as documentation generation |

### Releasing

A new version is released when a merge or push to `main` occurs.

We use the rules at [default-release-rules.js](https://github.com/semantic-release/commit-analyzer/blob/master/lib/default-release-rules.js) as our guide to when a series of commits should create a release.
