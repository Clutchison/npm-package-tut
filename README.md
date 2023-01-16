# Instructions (2023)

This repo was cribbed from Matt Pocock's YT video: https://www.youtube.com/watch?v=eh89VE3Mk5g

## Tools and Dependencies

### pnpm
https://pnpm.io/installation

### typescript
`pnpm add -D typescript` 

### tsup
`pnpm add -D tsup`.

### changeset
`pnpm add -D @changesets/cli`

## Files

### package.json
  ```json
  {
    "name": "my-package",
    "license": "MIT"
    "version": 0.0.1
    "main": "dist/index.js",
    "module": "dist/indext.mjs",
    "types": "dist/index.d.ts",
    "scripts": {
      "build": "tsup index.ts --format cjs,esm --dts",
      "lint": "tsc"
    },
  }
  ```

### index.ts
Example file: 
  ```ts
  export const add = (a: number, b: number) => {
    return a + b
  }
  ``` 

## Additional Setup

### tsc

- Run command: `pnpm tsc --init`
- Add to end of tsconfig.json: 
  ```json
    "noUncheckedIndexedAccess": true,
    "noEmit": true,
  ```

### git
- Run command: `git init` to intialize git.
- Create file .gitignore and add to it:
  ```
  node_modules
  dist
  ```

### changeset

`pnpm changeset init` 

## Usage

You can now use `pnpm run build` to generate .js and .mjs files.
  
You can use `pnpm run lint` to lint your code using tsc.
