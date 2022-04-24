<!-- LINTING SETUP -->

## VS Code Editor Linting Setup for NodeJs

In order to lint and format your code automatically according to popular airbnb style guide, I recommend you to follow the instructions. References are as below.

### Extensions

Install the below extensions:

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)

### Settings

Go to your Visual Studio Code `settings.json` file and add the below settings there:

```json
// config related to code formatting
"editor.defaultFormatter": "esbenp.prettier-vscode",
"editor.formatOnSave": true,
"[javascript]": {
  "editor.formatOnSave": false,
  "editor.defaultFormatter": null
},
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true,
  "source.organizeImports": true
},
"eslint.alwaysShowStatus": true
```

### Install Dev Dependencies

```sh
yarn add -D eslint prettier
npx install-peerdeps --dev eslint-config-airbnb-base
yarn add -D eslint-config-prettier eslint-plugin-prettier
```

### You should then set up a configuration file.

##### If you want, you can skip it and see the easy way below

```
npm init @eslint/config
```

or

```
yarn create @eslint/config
```

### The easiest way to do that is

Create a `.eslintrc.json` file in the project root and enter the below contents:

```json
{
  "env": {
    "browser": true,
    "commonjs": true,
    "es2021": true,
    "node": true
  },
  "extends": ["airbnb-base", "prettier"],
  "parserOptions": {
    "ecmaVersion": "latest"
  },
  "rules": {
    "no-console": 0,
    "indent": 0,
    "linebreak-style": 0,
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 2,
        "semi": true,
        "endOfLine": "auto"
      }
    ]
  },
  "plugins": ["prettier"]
}
```
