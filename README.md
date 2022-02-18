[![Piral Logo](https://github.com/smapiot/piral/raw/main/docs/assets/logo.png)](https://piral.io)

# Piral CLI Acceptance Tests

Integration tests for the `piral-cli` tool and its default bundler. Can be used as a test bench when implementing a new bundler, too.

## Status

[![Overall](https://smapiot.visualstudio.com/piral-pipelines/_apis/build/status/smapiot.piral-cli-integration-tests?branchName=main)](https://smapiot.visualstudio.com/piral-pipelines/_build/latest?definitionId=46&branchName=main)

| OS           | Node   | Status       |
| ------------ | ------ | ------------ |
| Linux        | 12.x   | [![Build Status](https://smapiot.visualstudio.com/piral-pipelines/_apis/build/status/smapiot.piral-cli-integration-tests?branchName=main&jobName=Job&configuration=Job%20linux_node_12)](https://smapiot.visualstudio.com/piral-pipelines/_build/latest?definitionId=46&branchName=main)   |
| Linux        | 14.x   | [![Build Status](https://smapiot.visualstudio.com/piral-pipelines/_apis/build/status/smapiot.piral-cli-integration-tests?branchName=main&jobName=Job&configuration=Job%20linux_node_14)](https://smapiot.visualstudio.com/piral-pipelines/_build/latest?definitionId=46&branchName=main)   |
| Linux        | 16.x   | [![Build Status](https://smapiot.visualstudio.com/piral-pipelines/_apis/build/status/smapiot.piral-cli-integration-tests?branchName=main&jobName=Job&configuration=Job%20linux_node_16)](https://smapiot.visualstudio.com/piral-pipelines/_build/latest?definitionId=46&branchName=main)   |
| Linux        | 17.x   | [![Build Status](https://smapiot.visualstudio.com/piral-pipelines/_apis/build/status/smapiot.piral-cli-integration-tests?branchName=main&jobName=Job&configuration=Job%20linux_node_17)](https://smapiot.visualstudio.com/piral-pipelines/_build/latest?definitionId=46&branchName=main)   |
| Windows      | 14.x   | [![Build Status](https://smapiot.visualstudio.com/piral-pipelines/_apis/build/status/smapiot.piral-cli-integration-tests?branchName=main&jobName=Job&configuration=Job%20windows_node_14)](https://smapiot.visualstudio.com/piral-pipelines/_build/latest?definitionId=46&branchName=main) |

## Important Links

* 📢 **[We are hiring!](https://smapiot.com/jobs)** - work with us on Piral, its ecosystem and our users
* 🌍 [Website](https://piral.io/) - learn more about Piral
* 📖 [Documentation](https://docs.piral.io/) - everything to get started and master micro frontends
* 🉐 **Help translating Piral!** - making PRs in the [documentation branch](https://github.com/smapiot/piral/tree/documentation)
* 🐞 [Issue Tracker](https://github.com/smapiot/piral/issues) - report bugs or suggest new features
* 🗨  [Forums](https://stackoverflow.com/questions/tagged/piral) - use the community support on StackOverflow
* 👪 [Community Chat](https://gitter.im/piral-io/community) - ask questions and provide answers in our Gitter room

## Testing Package

[![npm version](https://img.shields.io/npm/v/piral-cli-webpack.svg?style=flat)](https://www.npmjs.com/package/piral-cli-webpack)

The tests are also available as a drop-in package to test bundler plugins. You can install it with:

```sh
npm i @smapiot/piral-cli-integration-tests
```

Then run the tests using

```sh
npx piral-cli-tests <your-bundler-name>
```

If you don't specify the bundler name then the current working directory's *package.json* will be used to infer it.

## Tests

### Piral

-   ✅ Scaffold Piral instance
-   ✅ Run/debug Piral instance
-   ✅ Build Piral instance
-   ✅ Validate Piral instance (through snapshot compare)
-   ✅ Use Piral instance emulator for scaffolding locally
-   ✅ Change Piral instance while debugging (HMR)
-   ✅ Upgrade Piral instance from older (0.12.0 -> ENV) to recent version
-   ⏸️ Check Piral instance with browser extension (`piral-inspector`)

### Pilet

-   ✅ Scaffold pilet (using `sample-piral@next`)
-   ✅ Run/debug new pilet
-   ✅ Build pilet
-   ✅ Publish pilet (to temp. feed)
-   ✅ Validate pilet (through snapshot compare)
-   ✅ Change pilet while debugging (HMR)
-   ⏸️ Check pilet with browser extension (`piral-inspector`)

The publish pilet command uses:

```sh
pilet publish --api-key {key} --url https://feed.piral.cloud/api/v1/pilet/temp --fresh
```

It also can perform against a feed [hosted by the `sample-pilet-service`](https://github.com/smapiot/sample-pilet-service).

## Enviroment variables

| ENV              | description                        | default    |
| ---------------- | ---------------------------------- | ---------- |
| `CLI_VERSION`    | Version of the `piral-cli` package | `latest`   |
| `BUNDLER`        | Prefix of the bundler to use       |            |

## License

Piral is released using the MIT license. For more information see the [license file](./LICENSE).
