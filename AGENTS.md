# ComfyUI-GGUF Fork: AirPods Integration

## Overview

This is a fork of [city96/ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF) maintained for integration with the [radicazz/airpods](https://github.com/radicazz/airpods) project. This fork adds custom modifications and enhancements tailored to the AirPods workflow.

## Branch Structure

### `main`

- **Purpose**: Upstream tracking branch
- **Status**: Kept clean and synchronized with the original ComfyUI-GGUF repository
- **Usage**: Reference point only—do not work directly on this branch
- **Updates**: Periodically synced with upstream to pull latest changes

### `airpods`

- **Purpose**: Active development branch for AirPods integration
- **Status**: Primary working branch
- **Usage**: All modifications and feature development happens here
- **Target**: Interfaces ComfyUI-GGUF with the radicazz/airpods project

## Project Context

**ComfyUI-GGUF** provides GGUF quantization support for ComfyUI, enabling efficient loading of quantized models (Flux, Stable Diffusion, etc.) with reduced VRAM requirements.

This fork adapts the node pack to work seamlessly with the AirPods project, potentially through:

- Custom node additions or modifications
- Integration with AirPods' computational pipeline
- Optimizations specific to the AirPods workflow

## Development Workflow

1. Work on the `airpods` branch for all modifications
2. Commit with conventional prefixes (`feat:`, `fix:`, `docs:`, etc.)
3. Keep `main` clean—do not push development work to `main`
4. Periodically sync `main` with upstream if needed:

   ```bash
   git fetch upstream
   git checkout main
   git merge upstream/main
   ```

## Resources

- **Original Repository**: <https://github.com/city96/ComfyUI-GGUF>
- **AirPods Project**: <https://github.com/radicazz/airpods>
- **ComfyUI**: <https://github.com/comfyanonymous/ComfyUI>
- **GGUF Format**: <https://github.com/ggerganov/llama.cpp> (GGUF spec)

## Contributing Back

If improvements made in this fork would benefit the upstream project, consider opening a pull request to [city96/ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF). The clean `main` branch makes this straightforward.
