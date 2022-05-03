# rules-nodejs-supports-workers-issue
Reproduction for ts_project with supports_workers not failing the build when there are TypeScript errors

To reproduce:

```
yarn
bazel build //...
```