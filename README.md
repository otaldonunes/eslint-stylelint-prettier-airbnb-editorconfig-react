**Apparently the official creator was no longer active in the community, so I decided to make this modified version. If you are interested in suggesting, contributing or implementing something, feel free to do a PR.** _(Credits at the end)_

_If you have mastered any language and want to help translating the readme or correcting the translations already done, click on [this](https://github.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/issues/1) issue and/or do a PR._

## README Translation

- [Português](README.pt.md)
- [简体中文](README.zh-CN.md)
- [Espanõl](README.es.md)
- [Française](README.fr.md)

# Installation

1. Navigate to your app directory where you want to include this style configuration.

   ```bash
   cd my-app
   ```

2. Run this command inside your app's root directory. (_Note: this command executes the `automatic-config.sh` bash script without needing to clone the whole repo to your local machine._)

   ```bash
   exec 3<&1;bash <&3 <(curl https://raw.githubusercontent.com/otaldonunes/eslint-stylelint-prettier-airbnb-editorconfig-react/main/automatic-config.sh 2> /dev/null)
   ```

3. Make selections for your preference of package manager (_Npm, Yarn or Yarn Workspaces_), file format (_.js or .json_), max-line size, and trailing commas (_none, es5, all_).

4. Look in your project's root directory and notice the four newly added/updated config files:
   - `.eslintrc.js` (or `.eslintrc.json`) (_Install the `ESLint` extension, it can be easily added by pressing (Ctrl + P) in VS Code, pasting the following command (`ext install ext install dbaeumer.vscode-eslint`), and pressing enter._)
   - `.prettierrc.js` (or `.prettierrc.json`) (_Install the `Prettier - Code formatter` extension, it can be easily added by pressing (Ctrl + P) in VS Code, pasting the following command (`ext install esbenp.prettier-vscode`), and pressing enter._)
   - `.stylelintrc` (_Install the `stylelint` extension, it can be easily added by pressing (Ctrl + P) in VS Code, pasting the following command (`ext install stylelint.vscode-stylelint`), and pressing enter._)
   - `.editorconfig` (_Install the `EditorConfig for VS Code` extension, it can be easily added by pressing (Ctrl + P) in VS Code, pasting the following command (`ext install EditorConfig.EditorConfig`), and pressing enter._)

# Packages

### Main Packages

1. [ESlint](https://eslint.org/)
2. [Prettier](https://prettier.io/)
3. [Stylelint](https://stylelint.io/)

### Airbnb Configuration

1. [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
   - This package provides Airbnb's .eslintrc as an extensible shared config.
2. [eslint-plugin-jsx-a11y](https://github.com/evcohen/eslint-plugin-jsx-a11y) (Peer Dependency)
   - Static AST checker for accessibility rules on JSX elements.
3. [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) (Peer Dependency)
   - React specific linting rules for ESLint
4. [eslint-plugin-import](https://www.npmjs.com/package/eslint-plugin-import)
   - Support linting of ES2015+ (ES6+) import/export syntax, and prevent issues with misspelling of file paths and import names.
5. [stylelint-config-airbnb](https://www.npmjs.com/package/stylelint-config-airbnb)
   - This package provides Airbnb's .stylelintrc as an extensible shared config.
6. [eslint-plugin-react-hooks](https://www.npmjs.com/package/eslint-plugin-react-hooks)
   - This package provides the Rules of Hooks.
7. [babel-eslint](https://github.com/babel/babel-eslint)
   - A wrapper for Babel's parser used for ESLint.
   - We decided to include this since [Airbnb Style Guide uses Babel](https://github.com/airbnb/javascript#airbnb-javascript-style-guide-).

### ESlint, Prettier Integration

1. [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier)
   - Runs Prettier as an ESLint rule and reports differences as individual ESLint issues.
2. [stylelint-prettier](https://www.npmjs.com/package/stylelint-prettier)
   - Runs Prettier as a Stylelint rule and reports differences as individual Stylelint issues.
3. [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier)
   - Turns off all rules that are unnecessary or might conflict with Prettier.
4. [stylelint-config-prettier](https://www.npmjs.com/package/stylelint-config-prettier)

   - Turns off all rules that are unnecessary or might conflict with Prettier.

### Others

1. [eslint-plugin-html](https://www.npmjs.com/package/eslint-plugin-html)
   - A ESLint plugin to lint and fix inline scripts contained in HTML files.
2. [eslint-plugin-jest](https://www.npmjs.com/package/stylelint-prettier)
   - ESLint plugin for Jest.

# Created Configuration Files

Once files are created, you may edit to your liking.

### eslintrc(.js/.json)

- [more info](https://eslint.org/docs/user-guide/configuring)

```
{
"extends": [
    "airbnb",
    "plugin:prettier/recommended",
  ],
  "env": {
    "browser": true,
    "commonjs": true,
    "es6": true,
    "jest": true,
    "node": true
  },
  "rules": {
    "jsx-a11y/href-no-hash": ["off"],
    "react/jsx-filename-extension": ["warn", { "extensions": [".js", ".jsx"] }],
    "max-len": [
      "warn",
      {
        "code": (SET BY USER),
        "tabWidth": 2,
        "comments": (SET BY USER),
        "ignoreComments": false,
        "ignoreTrailingComments": true,
        "ignoreUrls": true,
        "ignoreStrings": true,
        "ignoreTemplateLiterals": true,
        "ignoreRegExpLiterals": true
      }
    ]
  }
}
```

### prettierrc(.js/.json)

- [more Info](https://prettier.io/docs/en/configuration.html)

```
{
  "printWidth": (SET BY USER),
  "singleQuote": true,
  "trailingComma": (SET BY USER)
}
```

### stylelintrc(.js/.json)

- [more Info](https://stylelint.io/user-guide/configure)

```
{
  "extends": ["stylelint-prettier/recommended", "stylelint-config-airbnb"]
}
```

### .editorconfig

- [more Info](https://editorconfig.org/#example-file)

```
root = true
  [*.{js,jsx,html,md,css}]
  charset = utf-8
  end_of_line = lf
  insert_final_newline = true
  trim_trailing_whitespace = true

  [*.{js,jsx,css}]
  indent_size = 2
  indent_style = space
```

---

This script was created by [Paulo Ramos](https://github.com/paulolramos), updated and modified with new features added by [Arthur Nunes](https://github.com/otaldonunes), [Martin Dobrev](https://github.com/RAMTO), [Darshan Gada](https://github.com/dr5hn), [Imed Adel](https://github.com/ImedAdel/). and inspired by Jeffrey Zhen's [tutorial](https://blog.echobind.com/integrating-prettier-eslint-airbnb-style-guide-in-vscode-47f07b5d7d6a).
