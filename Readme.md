# Ollama Multi-Model Tester (HTML Version)

A standalone web application for testing and comparing multiple Ollama models simultaneously. This tool allows you to test prompts across different models and compare their responses, with built-in memory management for efficient GPU utilization.

## Features

- **Multi-Model Testing**: Test multiple Ollama models simultaneously
- **Smart Memory Management**: Automatically unloads models when testing multiple models to optimize GPU memory
- **Real-Time Response Display**: See responses as they come in, with timing information
- **Prompt Management**:
  - Load prompts from XML files in the `prompts` folder
  - Enter custom prompts directly
  - View and edit loaded prompts
- **Visual Feedback**:
  - Loading animations
  - Response timing information
  - Organized model selection interface
  - Dark mode UI

## Prerequisites

- Ollama installed and running locally
- Web browser with JavaScript enabled
- Local HTTP server (for serving the HTML file)

## Quick Start

1. Make sure Ollama is running on your system
2. Place the `index.html` file in a directory with your `prompts` folder
3. Serve the directory using a local HTTP server, for example:
   ```bash
   python3 -m http.server 8000
   ```
4. Open your browser and navigate to `http://localhost:8000`

## Usage

1. **Select Models**:
   - Models are organized in two columns:
     - Left: Models with names ≤ 20 characters
     - Right: Models with longer names
   - Check one or more models to test

2. **Choose Prompt Source**:
   - Select a pre-defined prompt from the dropdown
   - Or choose "Custom Prompt" to enter your own

3. **Generate Responses**:
   - Click "Generate Responses"
   - Watch as responses appear in real-time
   - Each response includes generation time

## Prompt Files

Place your XML prompt files in the `prompts` folder. Files should follow this structure:
```xml
<prompt>
    Your prompt text here
</prompt>
```
Alternative tags supported: `content`, `text`, `description`

## Technical Details

- **Memory Management**: When multiple models are selected, `keep_alive: 0` is set to free GPU memory after each model
- **API Integration**: Direct integration with Ollama API endpoints:
  - `/api/tags` for model listing
  - `/api/generate` for text generation
- **Response Timing**: Measures and displays generation time for each model

## Browser Compatibility

Tested and working on:
- Chrome/Chromium (latest)
- Firefox (latest)
- Safari (latest)

## Contributing

Feel free to submit issues and enhancement requests!
