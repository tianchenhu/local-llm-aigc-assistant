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
graph TD
    A[User] -->|Text Prompt| B[Open WebUI Interface]
    B --> C[Local Multimodal AI System]
    C --> D[Qwen2.5 Conversation Module<br>(7B GGUF Quantized)]
    C --> E[Tavily Real-time Web Search]
    C --> F[ComfyUI Image Generation Engine]
    F --> G[Anima Anime Model<br>(anima-preview.safetensors)]
    F --> H[Text Encoders + VAE<br>(qwen_3_06b_base & qwen_image_vae)]
    D -->|Text Response| B
    E -->|Search Results| B
    G -->|Anime/Non-Realistic Image| B
    subgraph "Local Hardware Resources"
        I[RTX 4070 Laptop GPU<br>8GB VRAM]
    end
    C --> I
    style C fill:#f9f,stroke:#333,stroke-width:2px
    style I fill:#bbf,stroke:#333,stroke-width:2px

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
