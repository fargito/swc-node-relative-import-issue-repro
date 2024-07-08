# `swc-node` relative import reproduction

This is a basic reproduction for the swc relative import issue in https://github.com/swc-project/swc-node/issues/804

## Setup

```bash
nvm use # 20.15.0
pnpm i
pnpm test-type # everything is properly typed
pnpm test # should fail
```

## Reverting to a working state

In `package.json`, change the version of `@swc-node/register` to `1.10.0`:

```diff
-    "@swc-node/register": "^1.10.2",
+    "@swc-node/register": "^1.10.0",
```

Running `pnpm test` should not fail.