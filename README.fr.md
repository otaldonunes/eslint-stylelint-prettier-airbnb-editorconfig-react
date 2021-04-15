**Apparemment, le créateur officiel n'était plus actif dans la communauté, j'ai donc décidé de faire cette version modifiée. Si vous souhaitez suggérer, contribuer ou mettre en œuvre quelque chose, n'hésitez pas à faire un PR.**_(Crédits à la fin)_

_Si vous maîtrisez une langue et souhaitez aider à traduire le readme ou à corriger les traductions déjà effectuées, cliquez sur[cette](https://github.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/issues/1)émettre et / ou faire un PR._

## Traduction README

-   [Portugais](README.pt.md)
-   [Chinois simplifié](README.zh-CN.md)
-   [Espanõl](README.es.md)
-   [Française](README.fr.md)

# Installation

1.  Accédez au répertoire de votre application dans lequel vous souhaitez inclure cette configuration de style.

    ```bash
    cd my-app
    ```

2.  Exécutez cette commande dans le répertoire racine de votre application. (_Remarque: cette commande exécute le`automatic-config.sh`bash sans avoir besoin de cloner tout le dépôt sur votre machine locale._)

    ```bash
    exec 3<&1;bash <&3 <(curl https://raw.githubusercontent.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/main/automatic-config.sh 2> /dev/null)
    ```

3.  Faites des sélections en fonction de vos préférences de gestionnaire de packages (_Espaces de travail Npm, Yarn ou Yarn_), file format (_.js ou .json_), la taille de la ligne maximale et les virgules de fin (_aucun, es5, tous_).

4.  Regardez dans le répertoire racine de votre projet et notez les deux fichiers de configuration nouvellement ajoutés / mis à jour:
    -   `.eslintrc.js`(ou alors`.eslintrc.json`)
    -   `.prettierrc.js`(ou alors`.prettierrc.json`)
    -   `.editorconfig`(_Remarque: pour que cela fonctionne, vous devez installer le`EditorConfig for VS Code`extension, il peut être facilement ajouté en appuyant sur (Ctrl + P) dans VS Code, en collant la commande suivante (ext install EditorConfig.EditorConfig) et en appuyant sur Entrée._)

# Paquets

### Paquets principaux

1.  [ESlint](https://eslint.org/)
2.  [Plus jolie](https://prettier.io/)

### Airbnb Configuration

1.  [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
    -   Ce package fournit le .eslintrc d'Airbnb en tant que configuration partagée extensible.
2.  [eslint-plugin-jsx-a11y](https://github.com/evcohen/eslint-plugin-jsx-a11y)(Dépendance des pairs)
    -   Vérificateur AST statique pour les règles d'accessibilité sur les éléments JSX.
3.  [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react)(Dépendance des pairs)
    -   Réagissez aux règles de peluchage spécifiques pour ESLint
4.  [eslint-plugin-import](https://www.npmjs.com/package/eslint-plugin-import)(Dépendance des pairs)
    -   Prend en charge le peluchage de la syntaxe d'importation / exportation ES2015 + (ES6 +) et évite les problèmes d'orthographe des chemins de fichiers et des noms d'importation.
5.  [babel-eslint](https://github.com/babel/babel-eslint)
    -   Un wrapper pour l'analyseur de Babel utilisé pour ESLint.
    -   Nous avons décidé d'inclure cela depuis[Airbnb Style Guide utilise Babel](https://github.com/airbnb/javascript#airbnb-javascript-style-guide-).

### ESlint, une intégration plus jolie

1.  [eslint-plugin-plus joli](https://github.com/prettier/eslint-plugin-prettier)
    -   Exécute Prettier en tant que règle ESLint et signale les différences en tant que problèmes ESLint individuels.
2.  [eslint-config-plus jolie](https://github.com/prettier/eslint-config-prettier)
    -   Désactive toutes les règles inutiles ou susceptibles d'entrer en conflit avec Prettier.

# Fichiers de configuration créés

Une fois les fichiers créés, vous pouvez les modifier à votre guise.

### eslintrc (.js / .json)

-   [Plus d'informations](https://eslint.org/docs/user-guide/configuring)


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

### prettierrc (.js / .json)

-   [Plus d'informations](https://prettier.io/docs/en/configuration.html)


    {
      "printWidth": (SET BY USER),
      "singleQuote": true,
      "trailingComma": (SET BY USER)
    }

### .editorconfig

-   [Plus d'informations](https://editorconfig.org/#example-file)


    root = true
      [*.{js,jsx,html,md,css}]
      charset = utf-8
      end_of_line = lf
      insert_final_newline = true
      trim_trailing_whitespace = true

      [*.{js,jsx,css}]
      indent_size = 2
      indent_style = space

* * *

Ce script a été créé par[Paulo Ramos](https://github.com/paulolramos), mis à jour et modifié avec de nouvelles fonctionnalités ajoutées par[Arthur Nunes](https://github.com/otaldonunes),[Martin Dobrev](https://github.com/RAMTO),[Visualisation](https://github.com/dr5hn),[Imed Adel](https://github.com/ImedAdel/). et inspiré par Jeffrey Zhen[Didacticiel](https://blog.echobind.com/integrating-prettier-eslint-airbnb-style-guide-in-vscode-47f07b5d7d6a).
