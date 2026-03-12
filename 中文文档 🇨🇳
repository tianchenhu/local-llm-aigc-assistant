本地多模态 AI 聊天助手（带 Anima 动漫风格图像生成）

一个完全 本地部署、注重隐私的多模态 AI 系统，集成了大型语言模型、实时网页搜索和动漫风格图像生成能力。

系统支持：

中文/英文对话 AI（基于 Qwen2.5-7B GGUF 模型）

实时网页搜索（通过 Tavily API）

动漫风格文本生成图像（使用 Anima 模型 + ComfyUI）

该项目展示了 本地 LLM 部署、多模态集成、Docker 编排 以及 自定义图像生成工作流。

返回英文文档 🇺🇸

截图






技术栈

LLM：Qwen2.5-7B-Instruct（GGUF 量化模型）

图像生成：Anima 动漫风格 Stable Diffusion 模型，通过 ComfyUI 调用

前端 & 后端：Open WebUI（Docker）

网页搜索：Tavily API

容器化：Docker + Docker Compose

硬件测试：RTX 4070 笔记本（8GB 显存）

快速开始
git clone https://github.com/你的用户名/你的仓库名.git
cd 你的仓库名

# 复制并编辑配置文件（添加 Tavily API key）
cp docker-compose.example.yml docker-compose.yml

# 启动服务
docker compose up -d
使用说明

打开浏览器访问 http://localhost:7860 进入聊天界面。

在文本框输入中文或英文消息，即可与 AI 进行对话。

输入带有图像生成描述的内容，AI 会通过 Anima 模型生成动漫风格图片。

若要使用实时搜索功能，请确保在 docker-compose.yml 中正确配置 Tavily API Key。

项目亮点

本地 LLM 部署：不依赖云端 API，保证数据隐私

多模态融合：文本 + 图像生成 + 实时搜索

可扩展性：支持修改 ComfyUI 工作流自定义图像生成

Docker 一键运行：快速部署，无需手动环境配置

许可证

MIT License
