# dx-dark

`dx-dark` 是一个 VS Code 深色主题扩展，主要为C#做了优化。

## 特性

- Visual Studio 风格深色主题，视觉更贴近 C# 开发者常用配色习惯
- 面向 C# 开发场景优化，已适配 VS Code `tokenColors` 与 `semanticTokenColors`
- 对 C# 属性（property）做了突出显示（紫色）
- 对静态成员做了特殊处理（加粗）

## 开发

- 主题配置文件：`themes/dx-dark-color-theme.json`
- Rider 原始配色：`omake/dx_dark.icls`
- 修改主题后可在开发窗口执行 `Developer: Reload Window` 快速预览

### Token 命中排查（VS Code 内置工具）

在 VS Code 里可以用内置调试工具查看某个符号到底命中了哪条主题规则。

1. 把光标放到你想看的符号上（例如 `EmptySha256`）
2. 按 `Ctrl+Shift+P` 打开命令面板
3. 输入并执行 `Developer: Inspect Editor Tokens and Scopes`
4. 查看弹出的悬浮面板

重点关注：
- `semantic token type`（例如 `variable` / `property` / `field`）
- `modifiers`（例如 `readonly` / `static` / `declaration`）
- `TextMate scopes`（语法 scope 列表）
- 当前实际命中的主题规则

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

## 推荐字体
主字体使用Source Code Pro,中文字体Fallback到微软雅黑
```text
'Source Code Pro','Microsoft YaHei','Consolas','Courier New',monospace
```

## License

This project is licensed under **GLWTPL**:  
https://github.com/me-shaon/GLWTPL
