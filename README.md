# Default ntm settings

This repository will be all default settings for our dev stack

## VSCode

### Extensions

#### 1. Angular Language Service

- **What is it?**  
   This extension provides a rich editing experience for Angular templates, both inline and external templates including:
  1.1 Completions lists
  1.2 AOT Diagnostic messages
  1.3 Quick info
  1.4 Go to definition

- **How install?**
  `code --install-extension Angular.ng-template`

#### 2. DotENV

- **What is it?**
  VSCode .env syntax highlighting

- **How install?**
  `code --install-extension mikestead.dotenv`

#### 3. Docker for Visual Studio Code

- **What is it?**
  The Docker extension makes it easy to build, manage and deploy containerized applications from Visual Studio Code.

- **How install?**
  `code --install-extension ms-azuretools.vscode-docker`

#### 4. ESLint

- **What is it?**
  Integrates ESLint into VS Code. For this extension works you need to install `npm install -g eslint`

- **How install?**
  `code --install-extension dbaeumer.vscode-eslint`

#### 5. GitLens

- **What is it?**
  GitLens supercharges the Git capabilities built into Visual Studio Code. It helps you to visualize code authorship at a glance via Git blame annotations and code lens, seamlessly navigate and explore Git repositories, gain valuable insights via powerful comparison commands, and so much more.

- **How install?**
  `code --install-extension eamodio.gitlens`

#### 6. Prettier - Code formatter

- **What is it?**
  Prettier is an opinionated code formatter. It enforces a consistent style by parsing your code and re-printing it with its own rules that take the maximum line length into account, wrapping code when necessary.

- **How install?**
  `code --install-extension esbenp.prettier-vscode`

#### 7. TODO Hightlight

- **What is it?**
  Highlight TODO, FIXME and other annotations within your code.

  Sometimes you forget to review the TODOs you've added while coding before you publish the code to production. So I've been wanting an extension for a long time that highlights them and reminds me that there are notes or things not done yet.

- **How install?**
  `code --install-extension vscode-todo-highlight`

## EditConfig

### What is it?

- EditorConfig helps maintain consistent coding styles for multiple developers working on the same project across various editors and IDEs. The EditorConfig project consists of a file format for defining coding styles and a collection of text editor plugins that enable editors to read the file format and adhere to defined styles. EditorConfig files are easily readable and they work nicely with version control systems.

### Standard file

```
root = true
[*]
charset = utf-8
indent_style = space
indent_size = 2
insert_final_newline = true
trim_trailing_whitespace = true
quote_type = single
max_line_length = 100
[*.md]
max_line_length = off
trim_trailing_whitespace = false
```

## Angular project

#### 1. Eslint

- First make sure that eslint is configured in your vscode - [eslint in vscode](https://github.com/Microsoft/vscode-eslint)

- The version of tslint should be `>= 5.18.0`
- You should install the necessary dependencies:

```shell
$ npm install --save-dev eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin @typescript-eslint/eslint-plugin-tslint
```

- Migrating the rules from tslint to eslint, there is a lib for that:

```shell
$ npx tslint-to-eslint-config
```

- This command will generate a `.eslintrc.js` file, you should:
  > - check the generated log file `tslint-to-eslint-config.log`, and delete the presented rules (because they are not yet compatible)
- Configure command `lint` in scripts of `package.json`:
  > `"lint": "eslint -c .eslintrc.js --ext .ts <mySrcFolder>"`
- Remove `tslint.json` pf projetc

#### 2. prettier

- First make sure that prettier is configured in your vscode - [prettier in vscode](https://github.com/prettier/prettier-vscode)
- Install:
   ```sh
      $ npm i --save-dev prettier eslint-config-prettier eslint-plugin-prettier
   ```
- Create a `.prettierrc` file at the root of the project
- Inside it add the rules:

```json
{
  "printWidth": 120,
  "singleQuote": true,
  "useTabs": false,
  "tabWidth": 2,
  "semi": true,
  "bracketSpacing": true
}
```

## TODO

- [ ] Adding eslint file in js project
- [ ] Adding prettier file in js project
- [ ] Adding integration eslint prettier and editorconfig
- [ ] Adding vscode settings.json
- [ ] Configure eslint and prettier in angular project
