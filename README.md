# taskr-swc Plugin

**taskr-swc** is a plugin for [Taskr](https://github.com/lukeed/taskr) that uses the [SWC](https://swc.rs/) compiler to transform TypeScript and JavaScript files, providing support for Babel 7, ES6 modules, and TypeScript syntax. This plugin helps optimize build performance by using SWC, a fast alternative to Babel.

## Features

- Transforms TypeScript and JavaScript files using SWC.
- Supports dynamic imports and JSX/TSX syntax.
- Configurable for client-side or server-side environments.
- Provides ES6 module output with loose transpilation options.
- Strips file extensions or changes `.ts`/`.tsx` to `.js`.
- Supports source maps with proper file path mapping.

## Installation

To install the package, add it to your project using npm or yarn:

```bash
npm install taskr-swc
# or
yarn add taskr-swc
```

### Usage

```javascript

//taskfile.js

export async function build(task, opts) {
  await task
    .source('src/**/*.+(ts|tsx|js)')
    .swc({ dev: opts.dev, outDir: 'dist', baseUrl: 'src' })
    .target('dist')
    .source('src/**/*.+(cjs|json)')
    .target('dist')
  task.$.log('Compiled src files')
}
```
