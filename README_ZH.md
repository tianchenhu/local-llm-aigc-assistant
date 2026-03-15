# 本地多模态 AI 聊天助手（支持 Anima 动漫图像生成）

一个完全本地运行、注重隐私的个人 AI 系统，支持：
- 高质量中英文对话（Qwen2.5 7B GGUF 量化版）
- 实时联网搜索（Tavily API）
- 动漫/非写实风格文生图（Anima 模型，通过 ComfyUI 实现）

本项目作为一个 AIGC 方向的技术作品集示例，展示了本地大模型部署、多模态 AI 集成、Docker 容器化编排，以及自定义动漫风格图像生成工作流。

[English README 🇬🇧](README.md)

## 项目截图

![聊天界面](docs/screenshot-chat.png)  
![Anima 动漫图像生成](docs/screenshot-anima-gen.png)  
## 系统架构

```mermaid
flowchart TD

用户[用户] --> Web界面[Open WebUI 界面]

Web界面 --> 系统[本地多模态 AI 系统]

系统 --> 对话服务[对话服务]
对话服务 --> Qwen[Qwen2.5-7B GGUF 模型]
Qwen --> Ollama[Ollama 推理运行时]

系统 --> 搜索服务[联网搜索服务]
搜索服务 --> Tavily[Tavily API]

系统 --> 图像服务[图像生成服务]
图像服务 --> ComfyUI[ComfyUI 工作流引擎]
ComfyUI --> Anima[Anima 动漫模型]

对话服务 --> GPU[RTX 4070 Laptop GPU]
图像服务 --> GPU
```

## 技术栈

- 大语言模型：Qwen2.5-7B-Instruct（GGUF 量化）
- 图像生成：Anima（2B 参数动漫/非写实模型，safetensors 格式，ComfyUI 驱动）
- 用户界面 & 后端：Open WebUI（Docker 部署）
- 联网搜索：Tavily API
- 容器化：Docker + docker-compose
- 测试硬件：RTX 4070 Laptop（8GB 显存）

## 快速上手（Docker 一键启动）

```bash
# 1. 克隆仓库
git clone https://github.com/你的用户名/你的仓库名.git
cd 你的仓库名

# 2. 复制配置文件并修改（填入 Tavily API Key 等）
cp docker-compose.example.yml docker-compose.yml
# 编辑 docker-compose.yml，填入你的 Tavily Key

# 3. 启动所有服务
docker compose up -d
