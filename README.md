# TSX Bug reproduction

This repository contains the minimal amount of code to reproduce a confusing behavior
in the `tsx` runtime.

This repository has two branches. The `main` branch is set to CommonJS module type in
`package.json`. The `esm` branch is set to ES module type in `package.json`. The Typescript
configuration between the two branches is identical.

### Description of the bug

There's a variance in the behavior of the `tsx` runtime when the module type is set to `CommonJS`
and `ESM`. For `CommonSJ`, we get the result of `react-katex` as two named exports, but for `ESM`
we get the result as a default export. This shouldn't change based on `package.json` but only for
`tsconfig.json`.

You can see the exported value by running `yarn tsx index.tsx` after installing the dependencies with
`yarn`. The behavior remains unchanged even if you specify `--tsconfig=tsconfig.json`.

# LICENSE

The contents of this repository are licensed under the terms of the MIT License.
