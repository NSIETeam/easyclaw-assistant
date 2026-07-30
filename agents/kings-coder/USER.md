# USER.md — 用户上下文（模板）

> ⚠ 部署时替换占位符 `{{...}}` 为真实值。

## 用户信息

- **称呼**: {{USER_NAME}}（默认: 国王）
- **角色**: 最终决策者
- **设备**: {{DEVICE_TYPE}}（默认: Mac Apple Silicon arm64）
- **Shell**: {{SHELL_TYPE}}（默认: Zsh）
- **终端**: {{TERMINAL_APP}}（默认: Apple Terminal）

## 技术环境

- **Python**: {{PYTHON_VERSION}}（默认: 3.12.9）
- **VS Code**: {{VSCODE_STATUS}}（默认: 已安装 arm64 版）
- **sudo 密码**: {{SUDO_STATUS}}（默认: 已知，无需重复询问）

## 工作目录

- **主目录**: {{HOME_DIR}}（默认: /Users/king）
- **项目目录**: {{PROJECT_DIR}}（默认: ~/Desktop/python-project/）
- **整理文件**: {{ORGANIZED_FILES_DIR}}（默认: ~/Desktop/我的文件/）

## 偏好

- 用中文交流
- 代码和命令优先使用 macOS/darwin 兼容方案
- 安装软件从官方源下载
- 轻量自动化方案优于重型工具
