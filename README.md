# OpenClaw Direct Chat

直接通过命令行调用 OpenClaw AI 对话的 Web 界面，无需经过 Hermes Agent Gateway。

## 功能

- 网页端聊天界面，调用本地 OpenClaw CLI
- 跨平台支持（Windows / Linux）
- Flask 后端 + 简约 HTML 前端

## 快速启动

### Windows

双击运行 `start.bat`，然后浏览器打开 http://localhost:5002

### Linux / macOS

```bash
python3 app.py
```

然后浏览器打开 http://localhost:5002

## 依赖

- Python 3.8+
- OpenClaw CLI (`openclaw` 或 `openclaw.cmd`)
- Node.js（OpenClaw 运行时需要）

## 项目结构

```
openclaw-direct-chat/
├── app.py              # Flask 后端服务
├── start.bat           # Windows 启动脚本
├── static/
│   └── chat.html       # 聊天界面前端
└── README.md           # 本文件
```

## 原理

通过 Python `subprocess` 调用本地安装的 `openclaw agent` 命令行工具，将用户输入作为 prompt 传递，捕获 stdout 返回 AI 回复。避免了复杂的 WebSocket 认证和 Gateway 协议。

## 许可证

MIT
