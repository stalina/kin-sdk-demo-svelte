# kin-sdk-demo-vue

Demo of using the [kin-sdk](https://github.com/kin-sdk/kin-sdk) in a Svelte app.

## Project setup

```
yarn install
```

### Compiles and hot-reloads for development

```
yarn serve
```

### Compiles and minifies for production

```
yarn build
```
## known issue

When launching `npm run dev`, an error is thrown : 
````
rollup v2.60.0
bundles src/main.ts → public/build/bundle.js...
(node:7236) [DEP0148] DeprecationWarning: Use of deprecated folder mapping "./" in the "exports" field module resolution of the package at /<path>/kin-sdk-demo-svelte/node_modules/tslib/package.json.
Update this package.json to use a subpath pattern like "./*".
(Use `node --trace-deprecation ...` to show where the warning was created)
(!) Plugin node-resolve: preferring built-in module 'buffer' over local alternative at '/<path>/kin-sdk-demo-svelte/node_modules/buffer/index.js', pass 'preferBuiltins: false' to disable this behavior or 'preferBuiltins: true' to disable this warning
[!] Error: Unexpected token (Note that you need @rollup/plugin-json to import JSON files)
node_modules/axios/package.json (2:8)
1: {
2:   "name": "axios",
           ^
3:   "version": "0.21.4",
4:   "description": "Promise based HTTP client for the browser and node.js",
Error: Unexpected token (Note that you need @rollup/plugin-json to import JSON files)
    at error (/<path>/kin-sdk-demo-svelte/node_modules/rollup/dist/shared/rollup.js:158:30)
    at Module.error (/<path>/kin-sdk-demo-svelte/node_modules/rollup/dist/shared/rollup.js:12382:16)
    at Module.tryParse (/<path>/kin-sdk-demo-svelte/node_modules/rollup/dist/shared/rollup.js:12785:25)
    at Module.setSource (/<path>/kin-sdk-demo-svelte/node_modules/rollup/dist/shared/rollup.js:12688:24)
    at ModuleLoader.addModuleSource (/<path>/kin-sdk-demo-svelte/node_modules/rollup/dist/shared/rollup.js:22152:20)


[2021-11-13 20:51:14] waiting for changes...
````
