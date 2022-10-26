# Setup ESLint and Prettier for React

## Initialize ESLint

```bash
npx eslint --init
```

## Install ESLint and Prettier plugins

```bash
npm install prettier eslint-config-prettier eslint-plugin-prettier --save-dev
```

## Create ignore files

Create `.eslintignore` and `.prettierignore` files in the root directory of your project.
Add in the following lines:

**.eslintignore**

```bash
node_modules
build
```

**.prettierignore**

```bash
build
node_modules
js
```

## Update config file

Update `.eslintrc.json` file in the root directory of your project.
Add in the following lines:

**.eslintrc.json**

```json
{
  "plugins": ["react", "prettier"],
  "extends": ["react-app", "airbnb", "prettier"],
  "rules": {
    "prettier/prettier": [
      "error",
      {
        "singleQuote": true
      }
    ],
    "react/jsx-filename-extension": [
      "warn",
      {
        "extensions": [".js", ".jsx"]
      }
    ]
  }
}
```

## VSCode settings

1. Install the following extensions:

   - ESLint
   - Prettier - Code formatter

2. Make sure your settings.json file has the following lines:

**settings.json**

```json
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "[javascript]": {
    "editor.formatOnSave": false
  },
  "eslint.codeAction.showDocumentation": {
    "enable": true
  },
  "eslint.alwaysShowStatus": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
```
