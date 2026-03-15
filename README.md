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

User[User] --> WebUI[Open WebUI]

WebUI --> System[Local Multimodal AI System]

System --> LLM[LLM Service]
LLM --> Qwen[Qwen2.5-7B GGUF]
Qwen --> Ollama[Ollama Runtime]

System --> Search[Web Search Service]
Search --> Tavily[Tavily API]

System --> Image[Image Generation Service]
Image --> ComfyUI[ComfyUI]
ComfyUI --> Anima[Anima Model]

LLM --> GPU[RTX 4070 Laptop GPU]
Image --> GPU

```

## Tech Stack

- LLM: Qwen2.5-7B-Instruct (GGUF quantized)
- Image Generation: Anima anime-style Stable Diffusion model via ComfyUI
- UI & Backend: Open WebUI (Docker)
- Web Search: Tavily API
- Containerization: Docker + Docker Compose
- Hardware Tested: RTX 4070 Laptop (8GB VRAM)

---

## Quick Start (Conceptual)

1. Install Docker and Ollama.
2. Pull the LLM:
   ollama pull qwen2.5
3. Clone this repository and copy the example config:
   cp docker-compose.example.yml docker-compose.yml
4. Start services:
   docker compose up -d
5. Import the workflow in ComfyUI:
   workflows/anima_workflow.json
