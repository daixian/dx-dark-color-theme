# dx-dark

`dx-dark` 是一个 VS Code 深色主题扩展，配色基于我的 Rider 主题 `omake/dx_dark.icls` 迁移而来。

## 特性

- Visual Studio 风格深色主题，视觉更贴近 C# 开发者常用配色习惯
- 面向 C# 开发场景优化，已适配 VS Code `tokenColors` 与 `semanticTokenColors`
- 对 C# 属性（property）做了突出显示（紫色 + 加粗）

## 安装与使用

### 方式 1：扩展开发模式（本地调试）

1. 用 VS Code 打开本项目目录
2. 按 `F5` 启动 `Extension Development Host`
3. 在新窗口按 `Ctrl+K Ctrl+T`，选择 `DX Dark`

### 方式 2：打包后安装（VSIX）

1. 在项目根目录执行：

```bash
npx -y @vscode/vsce package
```

2. 在 VS Code 中打开扩展面板，选择 `Install from VSIX...`
3. 选择生成的 `.vsix` 文件并安装
4. 在主题选择中切换到 `DX Dark`

## 开发

- 主题配置文件：`themes/dx-dark-color-theme.json`
- Rider 原始配色：`omake/dx_dark.icls`
- 修改主题后可在开发窗口执行 `Developer: Reload Window` 快速预览

## CI 构建

仓库已提供 GitHub Actions 工作流：`.github/workflows/ci.yml`

- 触发时机：`push`、`pull_request`、手动触发 `workflow_dispatch`
- 构建内容：校验主题 JSON + 打包 VSIX
- 产物下载：在 Actions 构建结果中下载 `dx-dark-vsix` artifact

## 目录结构

```text
.
├─ themes/
│  └─ dx-dark-color-theme.json
├─ omake/
│  └─ dx_dark.icls
└─ package.json
```

## License

This project is licensed under **GLWTPL**:  
https://github.com/me-shaon/GLWTPL
