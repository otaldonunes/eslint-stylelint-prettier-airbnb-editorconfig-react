**Aparentemente, o criador oficial não estava mais ativo na comunidade, então decidi fazer esta versão modificada. Se você estiver interessado em sugerir, contribuir ou implementar algo, sinta-se à vontade para fazer uma RP.**_(Créditos no final)_

_Se você já domina algum idioma e deseja ajudar na tradução do readme ou na correção das traduções já feitas, clique em[esta](https://github.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/issues/1)emitir e / ou fazer um PR._

# Instalação

1.  Navegue até o diretório do seu aplicativo onde deseja incluir esta configuração de estilo.

    ```bash
    cd my-app
    ```

2.  Execute este comando dentro do diretório raiz do seu aplicativo. (_Nota: este comando executa o`automatic-config.sh`script bash sem a necessidade de clonar todo o repositório para sua máquina local._)

    ```bash
    exec 3<&1;bash <&3 <(curl https://raw.githubusercontent.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/main/automatic-config.sh 2> /dev/null)
    ```

3.  Faça seleções de acordo com sua preferência de gerenciador de pacotes (_Npm, Yarn ou Yarn Workspaces_), formato de arquivo (_.js ou .json_), tamanho máximo da linha e vírgulas finais (_nenhum, es5, todos_).

4.  Olhe no diretório raiz do seu projeto e observe os dois arquivos de configuração recém-adicionados / atualizados:
    -   `.eslintrc.js`(ou`.eslintrc.json`)
    -   `.prettierrc.js`(ou`.prettierrc.json`)
    -   `.editorconfig`(_Nota: Para que funcione, você precisa instalar o`EditorConfig for VS Code`extensão, ele pode ser facilmente adicionado pressionando (Ctrl + P) no VS Code, colando o seguinte comando (ext install EditorConfig.EditorConfig) e pressionando enter._)

# Pacotes

### Pacotes Principais

1.  [ESlint](https://eslint.org/)
2.  [Mais bonita](https://prettier.io/)

### Configuração do Airbnb

1.  [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
    -   Este pacote fornece .eslintrc do Airbnb como uma configuração compartilhada extensível.
2.  [eslint-plugin-jsx-a11y](https://github.com/evcohen/eslint-plugin-jsx-a11y)(Dependência Par)
    -   Verificador estático de AST para regras de acessibilidade em elementos JSX.
3.  [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react)(Dependência Par)
    -   Reaja as regras de linting específicas para ESLint
4.  [eslint-plugin-import](https://www.npmjs.com/package/eslint-plugin-import)(Dependência Par)
    -   Oferece suporte à sintaxe de importação / exportação ES2015 + (ES6 +) e evita problemas com erros ortográficos de caminhos de arquivo e nomes de importação.
5.  [babel-eslint](https://github.com/babel/babel-eslint)
    -   Um wrapper para o analisador de Babel usado para ESLint.
    -   Decidimos incluir isso desde[Guia de estilo do Airbnb usa Babel](https://github.com/airbnb/javascript#airbnb-javascript-style-guide-).

### ESlint, integração mais bonita

1.  [eslint-plugin-mais bonito](https://github.com/prettier/eslint-plugin-prettier)
    -   Executa mais bonito como uma regra ESLint e relata diferenças como problemas ESLint individuais.
2.  [eslint-config-mais bonito](https://github.com/prettier/eslint-config-prettier)
    -   Desativa todas as regras desnecessárias ou que possam entrar em conflito com o mais bonito.

# Arquivos de configuração criados

Uma vez que os arquivos são criados, você pode editá-los ao seu gosto.

### eslintrc (.js / .json)

-   [mais informações](https://eslint.org/docs/user-guide/configuring)


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

-   [mais informações](https://prettier.io/docs/en/configuration.html)


    {
      "printWidth": (SET BY USER),
      "singleQuote": true,
      "trailingComma": (SET BY USER)
    }

### .editorconfig

-   [mais informações](https://editorconfig.org/#example-file)


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

Este script foi criado por[Paulo Ramos](https://github.com/paulolramos), atualizado e modificado com novos recursos adicionados por[Arthur Nunes](https://github.com/otaldonunes),[Martin Dobrev](https://github.com/RAMTO),[Visualização](https://github.com/dr5hn),[Justiça batizada](https://github.com/ImedAdel/). e inspirado por Jeffrey Zhen's[tutorial](https://blog.echobind.com/integrating-prettier-eslint-airbnb-style-guide-in-vscode-47f07b5d7d6a).
