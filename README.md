## PNPM Workspaces use-node-version example

This is an auxiliary example for a discussion of limitation in the pnpm's support of the `use-node-version` feature in workspaces.

The root (workspace) should use Node.js v18.14.0, `packages/a` should use Node.js v16.16.0, and `packages/b` should use Node.js v18.14.1, but during the execution from the workspace, only the version specified in the root's `.npmrc` is used. If root `.npmrc` is missing - the global version will be used. None of the packages will use their own version.

To reproduce run:
```bash
pnpm run -r test
```
