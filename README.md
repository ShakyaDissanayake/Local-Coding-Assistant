# Local Coding Assistant 🚀

**Local Coding Assistant** is a Python-based solution that allows developers to leverage the power of Large Language Models (LLMs) like Ollama's Qwen 2.5 Coder, **locally** without sharing any of their code or data with external providers. The assistant helps in code generation, modification, and answering questions about the codebase directly on your local machine.

This project is designed to address the issue of data privacy when using online coding assistants like GitHub Copilot, by enabling companies or developers to use LLMs locally, ensuring no code is sent to third-party servers.

---

## ✨ Features

- 🔒 **Local LLM Execution**: Run LLM models locally, avoiding any data sharing.
- ⚙️ **Customizable**: Easily integrate different LLMs through Ollama's platform.
- 📂 **Codebase Analysis**: Analyze and interact with Python repositories, with context-sensitive answers based on the codebase.
- 🤖 **Agent System**: A Python agent that uses LLMs to answer questions, suggest code improvements, and provide code snippets.
- 💻 **CLI Interface**: A simple command-line interface (CLI) to interact with the assistant.

---

## 🛠️ Installation

Follow these steps to install and set up **Local Coding Assistant** on your local machine:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/local-coding-assistant.git
   cd local-coding-assistant
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. **Install required dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Install Ollama:**
   Make sure you have Ollama installed. Follow the [Ollama setup guide](https://ollama.com/) to install it.

---

## 🚀 Usage

Once the setup is complete, you can start using the **Local Coding Assistant** via the command-line interface (CLI).

1. Ensure that your environment is activated and dependencies are installed.
2. To run the assistant, use the following command:

   ```bash
   python cli.py --source-code-path /path/to/your/python/repo --agent-type SINGLE_LLM --llm-provider OLLAMA --llm-model qwen2.5-coder:7b-instruct
   ```

   - Replace `/path/to/your/python/repo` with the path to your Python repository.
   - `--agent-type` can be `SINGLE_LLM`, which is the only option currently available.
   - `--llm-provider` specifies which LLM provider to use. Here, we're using Ollama.
   - `--llm-model` specifies the LLM model. In this case, `qwen2.5-coder:7b-instruct`.

3. The assistant will load the repository and enter a loop where you can interact with it by typing your questions.

   - Type your question or command and hit enter.
   - To exit the assistant, type `exit`.

---

## 🗂️ Project Structure

Here’s a breakdown of the project structure:

```
local-coding-assistant/
│
├── cli.py                      # Entry point for the CLI application.
├── py_coding_assistant/        # Core library files.
│   ├── agents.py               # Defines agents (SingleLLMAgent).
│   ├── llms/                   # Contains implementations of various LLMs.
│   │   ├── __init__.py
│   │   ├── factory.py          # LLM factory to create LLMs.
│   │   ├── ollama.py           # Ollama LLM implementation.
│   │   ├── anthropic.py        # Placeholder for Anthropic LLM (if used).
│   │   ├── dummy.py            # Dummy LLM for testing purposes.
│   ├── repo.py                 # Handles loading and analyzing Python repositories.
├── requirements.txt            # List of dependencies.
├── .env                        # Environment variables.
└── README.md                   # This README file.
```

---

## 🌱 Environment Setup

### Dependencies

The project requires the following Python packages:

- `typer`: For building the command-line interface.
- `loguru`: For logging.
- `gitingest`: For repository ingestion.
- `ollama`: For accessing Ollama's LLM models locally.
- `python-dotenv`: For managing environment variables.

Install all dependencies by running:

```bash
pip install -r requirements.txt
```

### Ollama Setup

This project uses the Ollama platform to run LLMs locally. Make sure you have Ollama installed by following these steps:

1. Visit [Ollama](https://ollama.com/) and download the installer for your operating system.
2. Follow the installation instructions and ensure the Ollama client is running.

---

## 🤝 Contributing

We welcome contributions! If you’d like to contribute to **Local Coding Assistant**, please fork the repository and submit a pull request. Here are some ways you can contribute:

- **🐛 Report Issues**: If you encounter bugs or problems, please create an issue.
- **✨ Feature Requests**: Suggest features that could make the assistant more useful.
- **🛠️ Fix Bugs**: Help improve the codebase by fixing bugs or improving documentation.

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

---

## 💡 Additional Notes

- **LLM Models**: By default, this project uses the `qwen2.5-coder:7b-instruct` model, but you can customize this by providing a different model through the `--llm-model` parameter in the CLI.
- **Data Privacy**: This project ensures your data stays local, preventing it from being shared with third-party servers.

---

Enjoy building with **Local Coding Assistant**! 🛠️💡
