# Planet Decred Chat

This is the repository for the [Planet Decred chat](https://chat.planetdecred.org/) web.

## Build from source

### Requirements:
- `node` is at least v10.x.
- `yarn` if not present already.

First clone and build `matrix-js-sdk`:

``` bash
$ git clone https://github.com/matrix-org/matrix-js-sdk.git
$ pushd matrix-js-sdk
$ git checkout v9.2.0
$ yarn link
$ yarn install
$ popd
```

Then similarly with `matrix-react-sdk`:

```bash
$ git clone https://github.com/planetdecred/matrix-react-sdk.git
$ pushd matrix-react-sdk
$ yarn link
$ yarn link matrix-js-sdk
$ yarn install
$ popd
```

Finally:

```bash
$ git clone https://github.com/planetdecred/element-web.git
$ cd element-web
$ yarn link matrix-js-sdk
$ yarn link matrix-react-sdk
$ yarn install

Configure the app by copying config.sample.json to config.json and modifying it. See the configuration docs for details.

$ yarn dist (yarn build on Windows)
```

This build all the necessary files into the `webapp` directory.
 
To run on a live server, use `$ yarn run` command instead of `$ yarn dist` and open http://127.0.0.1:8080/. 
