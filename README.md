# ComfyUI-GGUF for AirPods

GGUF quantization support for ComfyUI, forked and customized for integration with the [radicazz/airpods](https://github.com/radicazz/airpods) project.

## What is this?

This fork provides custom nodes for loading GGUF-quantized models in ComfyUI. Instead of loading full-precision models that consume 16-24GB+ of VRAM, you can use quantized versions that run efficiently on lower-end GPUs with significantly reduced memory footprint.

**Key benefits:**
- 4-8x smaller model files via quantization
- 50-75% VRAM reduction compared to full models
- Support for transformer-based models like Flux, Stable Diffusion 3.5, and others
- T5 text encoder quantization included for additional VRAM savings

## Installation

> [!IMPORTANT]  
> Ensure your ComfyUI version supports custom ops for UNET loading.

### Standard Installation

```bash
cd ComfyUI/custom_nodes
git clone https://github.com/radicazz/comfyui-gguf
cd comfyui-gguf
pip install -r requirements.txt
```

### Windows Standalone ComfyUI

From your `ComfyUI_windows_portable` folder:

```bash
git clone https://github.com/radicazz/comfyui-gguf ComfyUI/custom_nodes/comfyui-gguf
.\python_embeded\python.exe -s -m pip install -r .\ComfyUI\custom_nodes\comfyui-gguf\requirements.txt
```

### macOS Note

On macOS Sequoia, use torch 2.4.1 (2.6.X nightly can cause buffer errors). See the [original repo issues](https://github.com/city96/ComfyUI-GGUF/issues/107) for workarounds.

## Quick Start

1. **Place quantized models** in `ComfyUI/models/unet/` (`.gguf` files)
2. **Use the GGUF loader nodes** from the `bootleg` category in your workflows
3. **Load CLIP/T5 encoders** using `CLIPLoader (GGUF)` nodes for additional VRAM savings

## Workflow Templates

ComfyUI picks up templates from `example_workflows/` and shows them under "Browse Templates".
Start with:
- `example_workflows/flux-dev-gguf-simple.json`
- `example_workflows/flux-dev-gguf-simple.toml`

## Getting Quantized Models

Pre-quantized models available from the original project:

- [Flux 1.0 dev](https://huggingface.co/city96/FLUX.1-dev-gguf) (Q4, Q6, Q8 variants)
- [Flux 1.0 schnell](https://huggingface.co/city96/FLUX.1-schnell-gguf)
- [Stable Diffusion 3.5 large](https://huggingface.co/city96/stable-diffusion-3.5-large-gguf)
- [Stable Diffusion 3.5 turbo](https://huggingface.co/city96/stable-diffusion-3.5-large-turbo-gguf)
- [T5 v1.1-xxl encoder](https://huggingface.co/city96/t5-v1_1-xxl-encoder-gguf)

Recommended starting point: **Q4 or Q6** quantization for best quality/speed tradeoff on consumer GPUs.

## Quantization Guide

To create your own quantized models, see the [`tools/` folder](./tools) for conversion scripts.

## About This Fork

This is an active fork of [city96/ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF) adapted for the AirPods project workflow. See [`AGENTS.md`](./AGENTS.md) for branch structure and development guidelines.

**Branch info:**
- `main` — Upstream tracking (kept clean)
- `airpods` — Active development (default branch)

## Upstream Reference

- Original repo: [city96/ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF)
- GGUF format: [llama.cpp](https://github.com/ggerganov/llama.cpp)
- ComfyUI framework: [comfyanonymous/ComfyUI](https://github.com/comfyanonymous/ComfyUI)
- GGUF spec: [ggerganov/ggml](https://github.com/ggerganov/ggml)

## License

Apache 2.0 (inherited from upstream)
