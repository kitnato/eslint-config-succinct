# eslint-config-functional

An [ESLint](https://eslint.org/) configuration library for projects based on React 18+ with Typescript 4+.

## Disclaimer

This is an exhaustive and **opinionated** ESLint config that enforces consistent usage of ES6 & [strict](https://typescript-eslint.io/linting/configs/#strict) Typescript [functional programming](https://en.wikipedia.org/wiki/Functional_programming) paradigms. It encourages adherence to best practices and restricts certain language features that are prone to anti-patterns.

Notable linting rules include:

- `class` declarations are disallowed
- `interface` declarations are disallowed
- Only `enum` non-literal declarations are allowed
- Only `const` variable declarations are allowed
- Object keys and component props are sorted alphabetically

## Installation

First, install this package alongside `eslint`:

```sh
npm install -D @cneuro/eslint-config-functional eslint
```

Next, create the `.eslintrc.json` configuration file at the root of your project:

```json
{
  "extends": "@cneuro/eslint-config-functional",
}
```

Remember to [set](https://eslint.org/docs/latest/user-guide/configuring/ignoring-code) here any `ignorePatterns` if you require them beyond the standard `build` and `dist` folders, along with any other config overrides.

## Usage

Once installed, you can run any `eslint` command.

You may also define scripts that will lint, fix and format your files to help automate your workflow.

For example, in your `package.json`, add the following under `scripts`:

```json
"scripts": {
  "lint-code": "eslint --fix --ext .ts,.tsx .",
}
```

## IDE setup

### VS Code

If you use Microsoft VS Code, you can add the following snippet at the top of your `.vscode/settings.json` to automatically run `eslint` and fix all issues whenever a file is saved.

```json
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true
}
```

## License

This work is licensed under the [GNU General Public License version 3](https://www.gnu.org/licenses/gpl-3.0.en.html).
