# 甩锅利器 - Cloudflare 错误页面生成器

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

一个开源的 Cloudflare 风格错误页面生成器工具。生成高度仿真的 Cloudflare 5xx 错误页面，让你的网站在出问题时可以优雅地"甩锅"给 Cloudflare。

## 在线演示

👉 [点击体验](https://mbilse.github.io/cepg/src/)

## 功能特性

- 🎯 支持多种错误代码：500、502、503、504、520-527
- 🎨 完美复刻 Cloudflare 错误页面样式
- ✏️ 自定义域名、Ray ID 和错误消息
- 👀 实时预览生成效果
- 📋 一键复制 HTML 代码
- 💾 导出独立的静态 HTML 文件

## 快速启动

### 方法一：直接打开（推荐）

由于这是一个纯前端项目，你可以直接在浏览器中打开 `src/index.html` 文件：

```bash
# Windows
start src/index.html

# macOS
open src/index.html

# Linux
xdg-open src/index.html
```

或者直接双击 `src/index.html` 文件。

### 方法二：使用本地服务器

如果你需要完整的模块支持，可以使用任意静态文件服务器：

```bash
# 使用 Python
python -m http.server 8080 --directory src

# 使用 Node.js (需要先安装 serve)
npx serve src

# 使用 VS Code Live Server 插件
# 右键点击 src/index.html -> Open with Live Server
```

然后在浏览器中访问 `http://localhost:8080`

## 使用方法

1. 从下拉菜单选择错误代码（如 502 Bad Gateway）
2. 输入你的域名（可选）
3. 点击"生成"按钮创建 Ray ID，或手动输入
4. 添加自定义错误消息（可选）
5. 实时预览右侧面板中的效果
6. 点击"复制 HTML"复制代码，或点击"导出文件"下载 HTML 文件

## 运行测试

```bash
# 安装依赖
npm install

# 运行测试
npm test

# 监听模式运行测试
npm run test:watch
```

## 项目结构

```
src/
├── index.html          # 主页面
├── styles.css          # 样式文件
├── app.js              # 主应用逻辑
├── config/
│   ├── errorCodes.js   # 错误代码定义
│   └── configManager.js # 配置管理器
├── generators/
│   ├── html.js         # HTML 生成器
│   └── rayId.js        # Ray ID 生成器
└── utils/
    ├── clipboard.js    # 剪贴板工具
    └── download.js     # 文件下载工具
```

## 许可证

MIT License
