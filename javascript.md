**请确保你已经完成了 [scoop 的安装](https://github.com/FloatingShuYin/development-environment-manual#%E5%AE%89%E8%A3%85-windows-%E5%8C%85%E7%AE%A1%E7%90%86%E5%B7%A5%E5%85%B7-scoop)**

**如果你遇到了问题请提一个 issues.**
## 安装 node 版本管理工具 [nvm(node version management)](https://github.com/nvm-sh/nvm)

1. 按快捷键 `Win + X + I` 打开 powershell 终端窗口, 执行以下命令, 以下载安装 nvm

    ```powershell
    sudo scoop install nvm -g
    ```
2. 执行以下命令, 以下载 node 最新长期支持版本 12.13.1.

    ```powershell
    nvm install 12.14.0
    ```
    如果下载卡住了, 请选中终端窗口敲击回车多次...
3. 下载完成后, 执行一下命令, 以使用 12.14.0 版本的 node.

    ```powershell
    sudo nvm use 12.14.0
    ```
    期间会弹出一次 UAC 获取权限的窗口, 请点击`是`给予管理员权限.

4. 执行以下命令, 以验证 node 是否成功安装.

    ```powershell
    node -v
    npm -v
    ```

## 安装 npm registry 镜像源管理工具 [nrm(NPM registry manager)](https://github.com/Pana/nrm)

1. 执行以下命令, 以将 nrm 安装到 npm 全局目录:
    ```powershell
    npm install -g nrm
    ```

2. 执行以下命令, 以验证安装:

    ```powershell
    nrm ls
    ```

## 安装 node-gyp 依赖的编译环境

1. 执行以下命令，以下载安装 jdk
    ```powershell
    scoop bucket add java
    sudo scoop install oraclejdk -g
    ```

2. 执行以下命令, 以安装执行 windows-build-tools:
    ```powershell
    sudo npm install --global windows-build-tools
    ```

## 安装编辑器: [vscode(visual studio code)](https://github.com/microsoft/vscode)

1. 在 powershell 终端窗口中执行以下命令,以下载安装 vscode 便携版.

    ```powershell
    scoop bucket add extras
    scoop install vscode-portable
    ```

2. 要想验证安装,安装完成后, 在终端窗口键入 `code` 以打开 vscode 编辑器.
3. 为鼠标右键添加 vscode 的上下文菜单, 执行以下命令:
    ```powershell
    start "C:\Support\Scoop\apps\vscode-portable\current\vscode-install-context.reg" # 请确保 C:\Support\Scoop 是你安装 scoop 时设置的局部安装目录, 如有不同, 请修改为你自己的路径.
    ```

### 配置集成终端

**请确保你已经完成了[git 的安装](https://github.com/FloatingShuYin/development-environment-manual#%E9%85%8D%E7%BD%AE-git)**

1. 打开 vscode 编辑器
2. 按快捷键 `Ctrl + Shift + P` 打开命令面板, 在顶部弹出的命令面板中键入 `preferences: Open Settings(JSON)` 回车执行.
3. 在打开的 settings.json 文件中加入以下字段:
```json
    "terminal.integrated.shell.windows": "C:\\Scoop\\apps\\git\\current\\bin\\bash.exe", // 请确保路径为你自己的 git 安装路径
    "terminal.integrated.shellArgs.windows": [
        "--login",
        "-i"
    ],
    "terminal.external.windowsExec": "C:\\Scoop\\apps\\git\\current\\bin\\bash.exe", // 请确保路径为你自己的 git 安装路径
    "terminal.integrated.cursorStyle": "underline", // 终端光标样式
    "terminal.integrated.cursorBlinking": true,
    "terminal.integrated.fontFamily": "'Fira Code', 'Sarasa Mono T CL', 'Cascadia Code', 'Hack'", // 终端字体
    "terminal.integrated.fontSize": 18, // 字体大小
   "workbench.colorCustomizations": {
        // 更多终端主题: https://glitchbone.github.io/vscode-base16-term/#/tomorrow-night
        "terminal.background": "#1D1F21",
        "terminal.foreground": "#C5C8C6",
        "terminalCursor.background": "#C5C8C6",
        "terminalCursor.foreground": "#C5C8C6",
        "terminal.ansiBlack": "#1D1F21",
        "terminal.ansiBlue": "#81A2BE",
        "terminal.ansiBrightBlack": "#969896",
        "terminal.ansiBrightBlue": "#81A2BE",
        "terminal.ansiBrightCyan": "#8ABEB7",
        "terminal.ansiBrightGreen": "#B5BD68",
        "terminal.ansiBrightMagenta": "#B294BB",
        "terminal.ansiBrightRed": "#CC6666",
        "terminal.ansiBrightWhite": "#FFFFFF",
        "terminal.ansiBrightYellow": "#F0C674",
        "terminal.ansiCyan": "#8ABEB7",
        "terminal.ansiGreen": "#B5BD68",
        "terminal.ansiMagenta": "#B294BB",
        "terminal.ansiRed": "#CC6666",
        "terminal.ansiWhite": "#C5C8C6",
        "terminal.ansiYellow": "#F0C674"
    },
    // 英文会使用 Fira Code 中文会使用 Sarasa Mono T CL
    "editor.fontFamily": "'Fira Code', 'Sarasa Mono T CL', 'Cascadia Code', 'Hack'",
```
5. 按快捷键 `Ctrl + Shift + P` 打开命令面板, 在顶部弹出的命令面板中键入 `Terminal: Create New Integrated Terminal` 回车执行以打开集成终端.
6. 现在你应该看到底部的终端面板弹出.

### 扩展

- [适用于 VS Code 的中文（简体）语言包](https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-zh-hans)
- [Settings Sync, 同步你的 vscode 扩展与设置](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)
- [Debugger for Chrome, 从 vscode 调试运行在谷歌 Chrome 中的 JavaScript 代码](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)
- [Auto Close Tag, 自动添加 HTML/XML 关闭标签](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
- [Auto Rename Tag, 自动重命名成对的 HTML/XML 标记](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
- [Color Highlight, 为你文件中使用的颜色值上色](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)
- [Color Info, 提供 CSS 颜色的快速信息](https://marketplace.visualstudio.com/items?itemName=bierner.color-info)
- [Document This, 自动为 TypeScript 和 JavaScript 文件生成详细的 JSDoc 注释。](https://marketplace.visualstudio.com/items?itemName=joelday.docthis)
- [ESLint, 将 ESLint 集成到 vscode 中](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [GitLens — Git supercharged, GitLens 增强了内置在 Visual Studio 代码中的 Git 功能](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
- [Guides, 为你的代码缩进添加各种缩进指南线](https://marketplace.visualstudio.com/items?itemName=spywhere.guides)
- [HTML CSS Support, 为 HTML 及其模板语言提供 CSS 支持](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css)
- [Import Cost, 在编辑器中内联显示导入包的大小](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)
- [Node.js Modules Intellisense, 在 import 语句中自动完成 JavaScript / TypeScript 模块的 Visual Studio 代码插件。](https://marketplace.visualstudio.com/items?itemName=leizongmin.node-module-intellisense)
- [Project Manager, 项目管理, 功能有点多自己看介绍吧](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager)
- [Rainbow Brackets, 对你代码中的括号添加颜色](https://marketplace.visualstudio.com/items?itemName=2gua.rainbow-brackets)
- [Sorting HTML and Jade attributes, 排序你的 HTML 属性](https://marketplace.visualstudio.com/items?itemName=mrmlnc.vscode-attrs-sorter)

你可以在这里搜索你需要的扩展: [Visual Studio系列产品的扩展](https://marketplace.visualstudio.com/VSCode)

### Hello World

1. 按快捷键 `Ctrl + Shift + P` 打开命令面板, 在顶部弹出的命令面板中键入 `Terminal: Create New Integrated Terminal` 回车执行以打开集成终端.
2. 在集成终端窗口, 键入 `cd ~` 回车, 然后键入 `cd desktop` 回车.
3. 继续键入 `mkdir hello-world` 回车以在桌面创建 `hello-world` 文件夹, 然后键入 `cd hello-world` 回车.
4. 继续键入 `touch index.js` 回车以在 `hello-world` 文件夹中创建 `index.js` 文件.
5. 继续键入 `code .` 回车以使用 vscode 编辑器打开 `hello-world` 文件夹.
6. 复制 `console.log('Hello World!')` 到 `index.js` 文件中, 然后按快捷键 `Ctrl + S` 保存文件
7. 鼠标选中集成终端, 键入 `node index.js` 回车以执行 `index.js` 脚本文件.
8. 你应该看到 `Hello World!` 在终端窗口中被打印出.
9. 在 vscode 中 调试 node.js 请参考这篇文章: https://zhuanlan.zhihu.com/p/43016278
   以及 vscode 官方文档: https://code.visualstudio.com/docs/nodejs/nodejs-debugging

## 在线编辑器: [CodePen](https://codepen.io/)

你可以使用在线编辑器: [CodePen](https://codepen.io/pen/) 来快速练习 HTML + CSS + JS:

这是一个使用例子: https://codepen.io/FloatingShuYin/pen/jjzBXb


### vscode 编辑器主题

推荐主题：

[tomorrow-and-tomorrow-night-operator-mono-theme](https://marketplace.visualstudio.com/items?itemName=chiragpat.tomorrow-and-tomorrow-night-operator-mono-theme)
![Tomorrow](https://raw.githubusercontent.com/chiragpat/tomorrow-and-tomorrow-night-operator-mono-theme/master/images/Tomorrow-preview.png)
![Tomorrow Night](https://raw.githubusercontent.com/chiragpat/tomorrow-and-tomorrow-night-operator-mono-theme/master/images/Tomorrow-Night-preview.png)
![Tomorrow Night Bright](https://raw.githubusercontent.com/chiragpat/tomorrow-and-tomorrow-night-operator-mono-theme/master/images/Tomorrow-Night-Bright-preview.png)
![Tomorrow Night Eighties](https://raw.githubusercontent.com/chiragpat/tomorrow-and-tomorrow-night-operator-mono-theme/master/images/eighties-preview.png)

用着这么养眼的主题,写代码简直就是一种享受...

想自己找找主题? [主题](https://marketplace.visualstudio.com/search?term=theme&target=VSCode&category=All%20categories&sortBy=Relevance)
