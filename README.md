# rules-nodejs-supports-workers-issue
Reproduction for ts_project with supports_workers not failing the build when there are TypeScript errors

To reproduce:

```
yarn
bazel build //package-1:tsc
```

Will see something like:

```
$ bazel build //package-1:tsc
INFO: Analyzed target //package-1:tsc (1 packages loaded, 5 targets configured).
INFO: Found 1 target...
INFO: From Compiling TypeScript project (worker mode) //package-1:tsc [tsc -p package-1/tsconfig.json]:
package-1/index.ts(1,7): error TS2322: Type 'number' is not assignable to type 'string'.

Target //package-1:tsc up-to-date:
  bazel-bin/package-1/index.js
  bazel-bin/package-1/index.js.map
INFO: Elapsed time: 3.699s, Critical Path: 3.47s
INFO: 41 processes: 15 internal, 1 darwin-sandbox, 24 local, 1 worker.
INFO: Build completed successfully, 41 total actions
```

Build succeeds, even though there is a TypeScript error