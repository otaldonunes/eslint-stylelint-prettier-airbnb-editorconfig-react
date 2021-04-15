**显然，官方创建者已不再活跃于社区中，因此我决定制作此修改版本。如果您对建议，贡献或实施感兴趣，请随时进行PR。**_（末尾的积分）_

_如果您精通任何语言，并且想要帮助翻译自述文件或更正已完成的翻译，请单击[这](https://github.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/issues/1)发布和/或进行PR。_

## 自述翻译

-   [葡萄牙语](README.pt.md)
-   [简体中文](README.zh-CN.md)
-   [西班牙语](README.es.md)
-   [法语](README.fr.md)

# 安装

1.  导航到要包含此样式配置的应用程序目录。

    ```bash
    cd my-app
    ```

2.  在您应用的根目录中运行此命令。 （_注意：此命令执行`automatic-config.sh`bash脚本，而无需将整个存储库克隆到本地计算机。_)

    ```bash
    exec 3<&1;bash <&3 <(curl https://raw.githubusercontent.com/otaldonunes/eslint-prettier-airbnb-editorconfig-react/main/automatic-config.sh 2> /dev/null)
    ```

3.  根据您对程序包管理器的偏好进行选择（_Npm，纱线或纱线工作区_）， 文件格式 （_.js或.json_），最大行大小和尾随逗号（_没有，es5，全部_).

4.  查看项目的根目录，并注意两个新添加/更新的配置文件：
    -   `.eslintrc.js`（或者`.eslintrc.json`)
    -   `.prettierrc.js`（或者`.prettierrc.json`)
    -   `.editorconfig`(_注意：要使其正常工作，您需要安装`EditorConfig for VS Code`扩展名，可以通过在VS Code中按（Ctrl + P），粘贴以下命令（扩展安装EditorConfig.EditorConfig）并按Enter来轻松添加。_)

# 配套

### 主要包装

1.  [ESlint](https://eslint.org/)
2.  [更漂亮](https://prettier.io/)

### Airbnb配置

1.  [eslint-config-airbnb](https://www.npmjs.com/package/eslint-config-airbnb)
    -   该软件包提供了Airbnb的.eslintrc作为可扩展的共享配置。
2.  [eslint-plugin-jsx-a11y](https://github.com/evcohen/eslint-plugin-jsx-a11y)（对等依赖）
    -   静态AST检查器，用于JSX元素上的可访问性规则。
3.  [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react)（对等依赖）
    -   对ESLint的特定掉毛规则做出反应
4.  [eslint-plugin-import](https://www.npmjs.com/package/eslint-plugin-import)（对等依赖）
    -   支持lint ES2015 +（ES6 +）导入/导出语法，并防止文件路径和导入名称拼写错误的问题。
5.  [巴别·埃斯林特](https://github.com/babel/babel-eslint)
    -   用于ESLint的Babel解析器的包装。
    -   我们决定将其包括在内，因为[Airbnb风格指南使用Babel](https://github.com/airbnb/javascript#airbnb-javascript-style-guide-).

### ESlint，更漂亮的集成

1.  [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier)
    -   将Prettier作为ESLint规则运行，并将差异报告为单个ESLint问题。
2.  [eslint-config-prettier](https://github.com/prettier/eslint-config-prettier)
    -   关闭所有不必要的或可能与Prettier冲突的规则。

# 创建的配置文件

创建文件后，您可以根据自己的喜好进行编辑。

### eslintrc（.js / .json）

-   [更多信息](https://eslint.org/docs/user-guide/configuring)


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

### prettierrc（.js / .json）

-   [更多信息](https://prettier.io/docs/en/configuration.html)


    {
      "printWidth": (SET BY USER),
      "singleQuote": true,
      "trailingComma": (SET BY USER)
    }

### .editorconfig

-   [更多信息](https://editorconfig.org/#example-file)


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

该脚本是由创建的[保罗·拉莫斯（Paulo Ramos）](https://github.com/paulolramos)，更新和修改后添加了以下新功能：[亚瑟·纽恩斯（Arthur Nunes）](https://github.com/otaldonunes),[马丁·杜波夫（Martin Dobrev）](https://github.com/RAMTO),[可视化](https://github.com/dr5hn),[受洗的正义](https://github.com/ImedAdel/)。并受到Jeffrey Zhen的启发[教程](https://blog.echobind.com/integrating-prettier-eslint-airbnb-style-guide-in-vscode-47f07b5d7d6a).
