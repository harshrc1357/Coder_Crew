# 🤖 Coder Crew - AI-Powered Code Generation System

An intelligent multi-agent AI system built with CrewAI that autonomously generates, executes, and validates Python code from natural language assignments.

![CrewAI](https://img.shields.io/badge/CrewAI-000000?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Gradio](https://img.shields.io/badge/Gradio-FF7C00?style=for-the-badge)

## 🚀 Features

- **Autonomous Code Generation**: AI agent that understands assignments and generates working Python code
- **Safe Code Execution**: Docker-based execution environment with timeout and retry mechanisms
- **End-to-End Automation**: Generates code, runs it, and captures output
- **YAML-Based Configuration**: Agents and tasks configured via YAML
- **Gradio Web Interface**: Simple UI for interacting with the coding agent
- **Error Handling**: Retry logic (max 3) with execution time limits (30s)

## 🏗️ Architecture

The system uses a **CrewAI** framework with a single specialized agent:

- **Python Developer Agent**
  - Plans the solution
  - Writes clean, efficient Python code
  - Executes code in a safe Docker environment
  - Validates output and provides results

## 📋 Prerequisites

- Python >=3.10 <3.13
- [UV](https://docs.astral.sh/uv/) package manager
- Docker Desktop
- OpenAI API key

## 🛠️ Installation

1. Install UV:
```bash
pip install uv
```

2. Install dependencies:
```bash
crewai install
```

3. Create a `.env` file in the project root:
```env
OPENAI_API_KEY=your_openai_api_key_here
```

4. Install and start Docker Desktop

## 🎯 Usage

Run from project root:
```bash
crewai run
```

Default assignment calculates the first 10,000 terms of the series `1 - 1/3 + 1/5 - 1/7 + ...` multiplied by 4.

## ⚙️ Configuration

- **Agents**: `src/coder/config/agents.yaml`
- **Tasks**: `src/coder/config/tasks.yaml`
- **Assignment**: Edit `src/coder/main.py`
- **Crew settings**: `src/coder/crew.py`
  - `code_execution_mode`: "safe" (Docker) or other modes
  - `max_execution_time`: maximum execution time in seconds
  - `max_retry_limit`: number of retry attempts

## 📁 Project Structure

```text
coder/
├── src/coder/
│   ├── main.py
│   ├── crew.py
│   ├── config/
│   │   ├── agents.yaml
│   │   └── tasks.yaml
│   └── tools/
├── knowledge/
├── output/
└── pyproject.toml
```

## 📤 Output

Generated code and results are saved to `output/code_and_output.txt`.

## 🛠️ Technologies

CrewAI, Python, Docker, Gradio, OpenAI GPT-4o-mini
