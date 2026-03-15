# Local Multimodal AI Chat Assistant with Anima Anime Image Generation

A fully local, privacy-focused multimodal AI system integrating a large language model, real-time web search, and anime-style image generation.

The system supports:

- Chinese/English conversational AI powered by Qwen2.5-7B (GGUF)
- Real-time web search via Tavily API
- Anime-style text-to-image generation using the Anima model through ComfyUI

The project demonstrates local LLM deployment, multimodal integration, Docker orchestration, and custom image generation workflows.

[中文文档 🇨🇳](README_ZH.md)

---

## Screenshots

![Chat Interface](docs/screenshot-chat.png)
![Anime Image Generation](docs/screenshot-anima-gen.png)
## System Architecture

```mermaid
flowchart TD

User[User] --> UI[Open WebUI]

UI --> Core[Local Multimodal AI System]

Core --> Chat[Dialogue Module]
Chat --> Qwen[Qwen2.5-7B GGUF]
Qwen --> Ollama[Ollama / llama.cpp]

Core --> Search[Web Search Module]
Search --> Tavily[Tavily API]

Core --> Image[Image Generation Module]
Image --> ComfyUI[ComfyUI Workflow Engine]
ComfyUI --> Anima[Anima Anime Model]

Core --> GPU[GPU Inference RTX 4070 Laptop]

---

## Tech Stack

- LLM: Qwen2.5-7B-Instruct (GGUF quantized)
- Image Generation: Anima anime-style Stable Diffusion model via ComfyUI
- UI & Backend: Open WebUI (Docker)
- Web Search: Tavily API
- Containerization: Docker + Docker Compose
- Hardware Tested: RTX 4070 Laptop (8GB VRAM)

---

## Quick Start

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# Copy and edit config (add Tavily API key)
cp docker-compose.example.yml docker-compose.yml

# Start services
docker compose up -d
