# @stacks/eslint-config

A shareable ESLint configuration for Stacks projects, now supporting the new [ESLint flat config format](https://eslint.org/docs/latest/use/getting-started). This config is designed for use with ESLint v9+ and the new `eslint.config.js`/`eslint.config.mjs` file format.

## Installation

```bash
npm install --save-dev eslint @stacks/eslint-config
yarn add --dev eslint @stacks/eslint-config
pnpm add --dev eslint @stacks/eslint-config
```

## Usage

1. **Create an `eslint.config.js` (or `eslint.config.mjs`) file in your project root:**

```js
// eslint.config.js
import stacks from '@stacks/eslint-config';

export default [...stacks];
```

2. **(Optional) Add Prettier config to your `package.json`:**

```json
{
  "prettier": "@stacks/prettier-config"
}
```

3. **Run ESLint:**

```bash
npx eslint .
```

## Overriding Rules

You can override or add rules in your `eslint.config.js` by adding additional config objects to the exported array:

```js
export default [
  ...stacks,
  {
    files: ['**/*.ts'],
    rules: {
      '@typescript-eslint/no-use-before-define': 'warn',
    },
  },
];
```

---

## Migration from eslintrc to Flat Config

Run the following command to migrate your project (and then add `...stacks` to the exported array manually):

```bash
npx  @eslint/migrate-config .eslintrc.json
yarn dlx @eslint/migrate-config .eslintrc.json
pnpm dlx @eslint/migrate-config .eslintrc.json
```

---

## References

- [ESLint: Getting Started](https://eslint.org/docs/latest/use/getting-started)
- [ESLint: Shareable Configs](https://eslint.org/docs/latest/extend/shareable-configs)
- [ESLint: Migration Guide](https://eslint.org/docs/latest/use/configure/migration-guide)
