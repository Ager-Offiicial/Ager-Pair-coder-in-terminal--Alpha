# Ager

An agentic coding assistant that works in your terminal using local LLMs from Ollama.

![Version](https://img.shields.io/badge/version-0.3.0-blue)

## What's New in v0.3.0

- **Ager Pro Agent**: New AI coding assistant with Gemini integration
- **Claude Agent**: AI coding assistant with Claude API support
- **Multiple API Providers**: Support for different AI model providers
- **Local Model Support**: Use local Ollama models with advanced agents
- **Enhanced Tools**: More powerful code analysis and file operations
- **Improved UI**: Better terminal display with rich formatting

## Prerequisites

- Python 3.6+
- [Ollama](https://ollama.ai/) installed and running
- One or more language models pulled into Ollama (e.g., codellama:13b, mistral:7b, etc.)
- For advanced agents (optional):
  - Google API key (for Ager Pro Agent with Gemini)
  - Anthropic API key (for Claude Agent)

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/Ager-Offiicial/Ager-Pair-coder-in-terminal--Alpha.git
   cd ager
   ```

2. Choose one of the installation methods:

   **Option 1: Pip installation**
   ```
   pip install -e .
   ```
   
   **Option 2: Windows batch file**
   ```
   install.bat
   ```
   
   **Option 3: PowerShell users (recommended for PowerShell)**
   ```
   .\install_powershell.bat
   ```
   This creates a PowerShell module that allows you to use the `ager` command directly in PowerShell.

## Usage

### Basic Commands

```
ager --model MODEL_NAME --chat       # Start a chat session
ager --model MODEL_NAME --agent      # Start an agent for coding tasks
ager --claude-agent                  # Start Claude Agent (requires API key)
ager --ager-pro-agent                # Start Ager Pro Agent (Gemini integration)
ager --list-models                   # Show available models
ager --no-color                      # Disable colored output
ager help                            # Show help information
```

### Windows Users

**CMD Users**: Run `run_ager.bat` for a convenient menu interface.

**PowerShell Users**: After running `install_powershell.bat`, you can use `ager` commands directly in PowerShell. 
Alternatively, use `.\Use-Ager.ps1` with arguments (the simplest approach).

### Chat Mode

Chat mode allows you to have a conversation with the LLM:

```
ager --model llama2:7b --chat
```

#### Chat Commands

While in chat mode, you can use these special commands:
- `exit` or `quit` - End the session
- `clear` - Clear chat history
- `save` - Save conversation to file
- `help` - Show available commands

### Agent Mode

Agent mode helps you generate code based on your requirements:

```
ager --model codellama:13b --agent
```

#### How Agent Mode Works

1. Describe what you want to build
2. The agent will generate code and list files it plans to create
3. You can view the full LLM response if needed
4. You'll be asked to confirm each file creation
5. The agent checks for existing files and handles directories automatically
6. After file creation, you can run executable files directly

### Ager Pro Agent

AI coding assistant supporting Google Gemini and local Ollama models.

## Features

- Interactive chat interface with AI models
- Local file system access for reading and writing code
- Terminal command execution
- Support for both Google Gemini and local Ollama models

## Installation

### Basic Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/ager-pro-agent.git
cd ager-pro-agent

# Install the package
pip install -e .
```

### Windows-specific Installation

For Windows users, you'll need the `pyreadline3` package:

```bash
pip install -e ".[windows]"
```

### Gemini Support

To use Google Gemini models:

```bash
pip install -e ".[gemini]"
```

## Usage

Run the agent with a local Llama model:

```bash
ager --model llama3:8b --ager-pro-agent
```

Or with Google Gemini:

```bash
ager --model gemini-pro --ager-pro-agent
```

## Configuration

The agent can be configured via a `config.yaml` file in your home directory:

```yaml
api_key: your_gemini_api_key  # Required for Gemini models
model: llama3:8b  # Default model
```

## Requirements

- Python 3.8 or higher
- Ollama (for local models)
- Google API key (for Gemini models)

## Setting Up Google API Key

To use the Gemini models, you'll need to set up a Google API key:

```bash
ager --ager-pro-setup YOUR_API_KEY
```

## Using Ollama Models

To use local Ollama models, make sure Ollama is installed and running on your system, then:

```bash
ager --model llama3:8b --ager-pro-agent --use-ollama
```

You can also set the AGER_OLLAMA_MODEL environment variable to specify the model:

```bash
set AGER_OLLAMA_MODEL=llama3:8b
ager --ager-pro-agent --use-ollama
```

## Available Commands

Start the agent:
```bash
ager --ager-pro-agent
```

Specify a model:
```bash
ager --ager-pro-model gemini-1.5-pro --ager-pro-agent
```

List available Gemini models:
```bash
ager --ager-pro-list-models
```

Set default model:
```bash
ager --ager-pro-set-default-model gemini-1.5-pro
```

## Chat Commands

- `/exit` or `/quit` - Exit the chat session
- `/help` - Show help information

## Troubleshooting

### Windows-specific Issues
- If you encounter `ModuleNotFoundError: No module named 'readline'`, run the Windows fix script as described above.

### Ollama Connection Issues
- Make sure Ollama is running locally at http://localhost:11434
- Check that the requested model is available in your Ollama installation

### API Key Issues
- Verify that your Google API key is correctly set up
- Check your API quota limits if you receive API error responses

## Examples

### Listing Available Models

```
ager --list-models
```

### Starting Chat Mode

```
ager --model mistral:7b --chat
```

### Using Agent Mode to Create and Run a Python Script

```
ager --model codellama:13b --agent
```

Then describe your coding task when prompted, such as: "Create a simple weather API client in Python"

### Using Ager Pro Agent with Gemini

```
ager --ager-pro-agent
```

### Using Claude Agent with a Local Model

```
ager --model llama3:8b --local --claude-agent
```

### Automatic Model Selection

If you don't specify a model, Ager will automatically use the first available model in your Ollama installation:

```
ager --chat
ager --agent
```

## Advanced Agents

Ager includes two advanced AI coding agents:

### Ager Pro Agent

Powered by Google's Gemini models with support for local Ollama models. Features include:
- Advanced code understanding and generation
- File system operations and terminal commands
- Rich terminal UI with syntax highlighting
- Support for both cloud and local models

See [AGER_PRO_README.md](AGER_PRO_README.md) for more details.

### Claude Agent

Powered by Anthropic's Claude with support for local Ollama models. Features include:
- Deep codebase understanding
- File editing and git integration
- Context-aware code generation
- Support for both API and local models

See [CLAUDE_AGENT_README.md](CLAUDE_AGENT_README.md) for more details.

## License

MIT 