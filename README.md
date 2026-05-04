# 🌟 AI 万能视频下载总结器（SaveAny）

<div align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-blue.svg" alt="Python Version">
  <img src="https://img.shields.io/badge/Vue-3-green.svg" alt="Vue Version">
  <img src="https://img.shields.io/badge/FastAPI-0.135+-teal.svg" alt="FastAPI Version">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License">
</div>

<br>

一个基于 AI 的视频下载和总结工具，支持从 1800+ 平台下载视频，并提供 AI 总结、思维导图和问答功能。

---

## ✨ 功能特性

| 功能 | 描述 |
|------|------|
| 🎬 **多平台视频解析和下载** | 基于 yt-dlp 支持 1800+ 网站，涵盖 B 站、YouTube、抖音等主流平台 |
| 🍪 **Cookie 支持** | 支持导入 `cookies.txt` 文件，可下载会员高清视频 |
| 🤖 **AI 视频总结** | 自动提取字幕并调用 DeepSeek 大模型生成总结摘要 |
| 🗺️ **AI 思维导图** | 基于视频内容自动生成交互式思维导图 |
| 💬 **AI 视频问答** | 基于视频内容进行自由问答 |
| 📝 **字幕导出** | 支持下载 SRT、VTT、TXT 等格式字幕 |

---

## 🛠️ 技术栈

### 前端
- <img src="https://img.shields.io/badge/Vue.js-3-4FC08D?logo=vue.js&logoColor=white" alt="Vue"> Vue 3
- <img src="https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?logo=javascript&logoColor=black" alt="JavaScript"> JavaScript
- <img src="https://img.shields.io/badge/Vite-7.0+-646CFF?logo=vite&logoColor=white" alt="Vite"> Vite
- <img src="https://img.shields.io/badge/Tailwind_CSS-4.0+-06B6D4?logo=tailwindcss&logoColor=white" alt="Tailwind"> Tailwind CSS

### 后端
- <img src="https://img.shields.io/badge/FastAPI-0.135+-009688?logo=fastapi&logoColor=white" alt="FastAPI"> FastAPI
- <img src="https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white" alt="Python"> Python 3.10+
- <img src="https://img.shields.io/badge/yt--dlp-latest-FF0000?logo=youtube&logoColor=white" alt="yt-dlp"> yt-dlp
- <img src="https://img.shields.io/badge/DeepSeek-AI-7B6EF6" alt="DeepSeek"> DeepSeek
- <img src="https://img.shields.io/badge/SQLite-Reserved-003B57?logo=sqlite&logoColor=white" alt="SQLite"> SQLite（预留）

---

## 🚀 快速开始

### 📋 前置要求

| 工具 | 版本要求 | 检查命令 | 安装方式 |
|------|----------|----------|----------|
| <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" width="80"> Python | ≥ 3.10 | `python3 --version` | [官网下载](https://www.python.org/downloads/) |
| <img src="https://img.shields.io/badge/Node.js-339933?logo=nodedotjs&logoColor=white" width="80"> Node.js | ≥ 18 | `node -v` | [官网下载](https://nodejs.org/en) |
| <img src="https://img.shields.io/badge/npm-CB3837?logo=npm&logoColor=white" width="80"> npm | ≥ 9 | `npm -v` | 随 Node.js 一起安装 |
| <img src="https://img.shields.io/badge/FFmpeg-007808?logo=ffmpeg&logoColor=white" width="80"> FFmpeg | 任意 | `ffmpeg -version` | [官网下载](https://ffmpeg.org/download.html) |

### 📦 安装步骤

```bash
# 克隆项目
git clone https://github.com/Criss36/free-video-downloader.git
cd free-video-downloader

# 安装后端依赖
cd backend
pip install -r requirements.txt

# 安装前端依赖
cd ../frontend
npm install
```

### 🔧 配置环境变量

```bash
cd backend
cp .env.example .env
```

编辑 `.env` 文件，填入你的配置：

```env
# ✅ 必填 - DeepSeek API Key，用于 AI 视频总结
DEEPSEEK_API_KEY=sk-你的api-key
```

### 🍪 Cookie 使用方法（可选）

使用浏览器插件 **Get Cookies.txt** 导出网站 Cookie，保存为 `backend/cookies.txt` 文件，即可下载需要登录的会员视频。

> ⚠️ Cookie 文件包含敏感信息，已加入 `.gitignore`，不会提交到版本控制。

### ▶️ 启动项目

```bash
# 启动后端（终端1）
cd backend
python main.py

# 启动前端（终端2）
cd frontend
npm run dev
```

访问 http://localhost:5173 即可使用。

---

## 📡 API 文档

后端启动后，访问以下地址查看 API 文档：

- 📚 Swagger UI: http://localhost:8000/docs
- 📖 ReDoc: http://localhost:8000/redoc

---

## ⚠️ 合规声明

本项目仅用于技术学习和研究目的，请用户仅下载自己拥有版权或已获得合法授权的内容（如备份自己上传的视频、下载公开授权的免版权素材等）。用户应自行遵守所在地区的法律法规及各平台的服务条款，开发者不对用户的使用行为承担任何法律责任。

---

## 📁 项目结构

```
free-video-downloader/
├── 📄 docs/                    # 文档
│   └── 📖 本地运行指南.md
├── 🔧 backend/                 # FastAPI 后端
│   ├── main.py              # 入口 + 路由 + dotenv 加载
│   ├── downloader.py        # yt-dlp 封装（视频解析/下载）
│   ├── douyin.py            # 抖音专用解析模块
│   ├── summarizer.py        # AI 总结模块（字幕提取 + DeepSeek）
│   ├── api_summarize.py     # AI 总结 API 路由
│   ├── database.py          # 数据库模块（预留）
│   ├── requirements.txt     # Python 依赖
│   ├── .env.example         # 环境变量示例
│   └── 📂 downloads/        # 临时下载目录
├── 🎨 frontend/              # Vue3 前端
│   ├── src/
│   │   ├── App.vue
│   │   ├── main.js
│   │   ├── style.css
│   │   ├── components/
│   │   └── api/
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
└── 📝 README.md
```

---

<div align="center">
  Made with ❤️ by Criss36
</div>
