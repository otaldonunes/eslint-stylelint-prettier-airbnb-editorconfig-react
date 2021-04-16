**Aparentemente, el creador oficial ya no estaba activo en la comunidad, así que decidí hacer esta versión modificada. Si está interesado en sugerir, contribuir o implementar algo, no dude en hacer un PR.**_(Créditos al final)_

_Si domina algún idioma y desea ayudar a traducir el archivo Léame o corregir las traducciones ya realizadas, haga clic en[esto](https://github.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/issues/1)emitir y / o hacer un PR._

## Traducción README

-   [portugués](README.pt.md)
-   [Chino simplificado](README.zh-CN.md)
-   [Espanõl](README.es.md)
-   [Francésa](README.fr.md)

# Instalación

1.  Navegue hasta el directorio de su aplicación donde desea incluir esta configuración de estilo.

    ```bash
    cd my-app
    ```

2.  Ejecute este comando dentro del directorio raíz de su aplicación. (_Nota: este comando ejecuta el`automatic-config.sh`bash sin necesidad de clonar todo el repositorio en su máquina local._)

    ```bash
    exec 3<&1;bash <&3 <(curl https://raw.githubusercontent.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/main/automatic-config.sh 2> /dev/null)
    ```

3.  Realice selecciones según sus preferencias de administrador de paquetes (_Espacios de trabajo de Npm, Yarn o Yarn_), formato de archivo (_.js o .json_), tamaño máximo de línea y comas finales (_ninguno, es5, todos_).

4.  Busque en el directorio raíz de su proyecto y observe los cuatro archivos de configuración recién agregados / actualizados:
    -   `.eslintrc.js`(o`.eslintrc.json`) (_Instala el`ESLint`extensión, se puede agregar fácilmente presionando (Ctrl + P) en VS Code, pegando el siguiente comando (`ext install ext install dbaeumer.vscode-eslint`) y presionando enter._)
    -   `.prettierrc.js`(o`.prettierrc.json`) (_Instala el`Prettier - Code formatter`extensión, se puede agregar fácilmente presionando (Ctrl + P) en VS Code, pegando el siguiente comando (`ext install esbenp.prettier-vscode`) y presionando enter._)
    -   `.stylelintrc`(_Instala el`stylelint`extensión, se puede agregar fácilmente presionando (Ctrl + P) en VS Code, pegando el siguiente comando (`ext install stylelint.vscode-stylelint`) y presionando enter._)
    -   `.editorconfig`(_Instala el`EditorConfig for VS Code`extensión, se puede agregar fácilmente presionando (Ctrl + P) en VS Code, pegando el siguiente comando (`ext install EditorConfig.EditorConfig`) y presionando enter._)

# Paquetes

### Paquetes principales

1.  [ESlint](https://eslint.org/)
2.  [Más bonita](https://prettier.io/)
3.  [Stylelint](https://stylelint.io/)

### Configuración de Airbnb

1.  [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
    -   Este paquete proporciona .eslintrc de Airbnb como una configuración compartida extensible.
2.  [eslint-plugin-jsx-a11y](https://github.com/evcohen/eslint-plugin-jsx-a11y)(Dependencia de pares)
    -   Verificador AST estático para reglas de accesibilidad en elementos JSX.
3.  [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react)(Dependencia de pares)
    -   Reaccionar reglas de pelusa específicas para ESLint
4.  [eslint-plugin-import](https://www.npmjs.com/package/eslint-plugin-import)
    -   Admite la sintaxis de importación / exportación de ES2015 + (ES6 +) y evita problemas con errores ortográficos en las rutas de archivo y los nombres de importación.
5.  [stylelint-config-airbnb](https://www.npmjs.com/package/stylelint-config-airbnb)
    -   Este paquete proporciona .stylelintrc de Airbnb como una configuración compartida extensible.
6.  [eslint-plugin-react-hooks](https://www.npmjs.com/package/eslint-plugin-react-hooks)
    -   Este paquete proporciona las Reglas de Hooks.
7.  [babel-eslint](https://github.com/babel/babel-eslint)
    -   Un contenedor para el analizador de Babel utilizado para ESLint.
    -   Decidimos incluir esto ya que[La guía de estilo de Airbnb usa Babel](https://github.com/airbnb/javascript#airbnb-javascript-style-guide-).

### ESlint, integración más bonita

1.  [eslint-plugin-más bonito](https://github.com/prettier/eslint-plugin-prettier)
    -   Se ejecuta Prettier como una regla de ESLint e informa las diferencias como problemas individuales de ESLint.
2.  [estilizado-más bonito](https://www.npmjs.com/package/stylelint-prettier)
    -   Se ejecuta Prettier como una regla de Stylelint e informa las diferencias como problemas individuales de Stylelint.
3.  [eslint-config-más bonito](https://github.com/prettier/eslint-config-prettier)
    -   Desactiva todas las reglas que son innecesarias o que pueden entrar en conflicto con Prettier.
4.  [stylelint-config-más bonito](https://www.npmjs.com/package/stylelint-config-prettier)
    -   Desactiva todas las reglas que son innecesarias o que pueden entrar en conflicto con Prettier.
5.  [eslint-plugin-html](https://www.npmjs.com/package/eslint-plugin-html)
    -   Un complemento de ESLint para eliminar y corregir scripts en línea contenidos en archivos HTML.

# Archivos de configuración creados

Una vez creados los archivos, puede editarlos a su gusto.

### eslintrc (.js / .json)

-   [más información](https://eslint.org/docs/user-guide/configuring)


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

### más bonitorc (.js / .json)

-   [más información](https://prettier.io/docs/en/configuration.html)


    {
      "printWidth": (SET BY USER),
      "singleQuote": true,
      "trailingComma": (SET BY USER)
    }

### stylelintrc (.js / .json)

-   [más información](https://stylelint.io/user-guide/configure)


    {
      "extends": ["stylelint-prettier/recommended", "stylelint-config-airbnb"]
    }

### .editorconfig

-   [más información](https://editorconfig.org/#example-file)


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

Este script fue creado por[Paulo Ramos](https://github.com/paulolramos), actualizado y modificado con nuevas funciones agregadas por[Arthur Nunes](https://github.com/otaldonunes),[Martín Dobrev](https://github.com/RAMTO),[Visualización](https://github.com/dr5hn),[Justicia bautizada](https://github.com/ImedAdel/). e inspirado por Jeffrey Zhen's[tutorial](https://blog.echobind.com/integrating-prettier-eslint-airbnb-style-guide-in-vscode-47f07b5d7d6a).
