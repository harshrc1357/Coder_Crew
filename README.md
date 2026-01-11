# Coder Crew - AI-Powered Code Generation System

An intelligent multi-agent AI system built with CrewAI that autonomously generates, executes, and validates Python code from natural language assignments. This project demonstrates advanced AI agent orchestration with safe code execution capabilities.

## 🚀 Features

- **Autonomous Code Generation**: AI agent that understands natural language assignments and generates working Python code
- **Safe Code Execution**: Docker-based execution environment with timeout and retry mechanisms
- **End-to-End Automation**: Complete workflow from assignment to code generation, execution, and output validation
- **YAML-Based Configuration**: Flexible agent and task configuration using YAML files
- **Gradio Web Interface**: User-friendly interface for interacting with the coding agent
- **Error Handling**: Built-in retry logic (max 3 retries) and execution time limits (30 seconds)

## 🏗️ Architecture

The system uses a **CrewAI** framework with a single specialized agent:

- **Python Developer Agent**: 
  - Plans the code structure
  - Writes clean, efficient Python code
  - Executes code in a safe Docker environment
  - Validates output and provides results

## 📋 Prerequisites

- Python >=3.10 <3.13
- [UV](https://docs.astral.sh/uv/) package manager
- Docker Desktop (for safe code execution)
- OpenAI API key

## 🛠️ Installation

1. **Install UV** (if not already installed):
  
   pip install uv
   2. **Install dependencies**:
   crewai install
   3. **Set up environment variables**:
   Create a `.env` file in the root directory:
   OPENAI_API_KEY=your_openai_api_key_here
   4. **Install Docker Desktop** (for code execution):
   - Download from [Docker Desktop](https://docs.docker.com/desktop/)
   - Ensure Docker is running before executing code

## 🎯 Usage

### Running the Crew

Execute the coding crew from the root directory:

crewai runThe default assignment will generate a Python program to calculate the first 10,000 terms of the series: `1 - 1/3 + 1/5 - 1/7 + ...` multiplied by 4.

### Customizing Assignments

Edit `src/coder/main.py` to change the assignment:

assignment = 'Your coding assignment here'### Configuration

#### Agents Configuration (`src/coder/config/agents.yaml`)

Customize the Python Developer agent's behavior, role, goals, and backstory.

#### Tasks Configuration (`src/coder/config/tasks.yaml`)

Define tasks, expected outputs, and output file locations.

#### Crew Configuration (`src/coder/crew.py`)

Modify crew settings:
- `code_execution_mode`: "safe" (Docker) or other modes
- `max_execution_time`: Maximum execution time in seconds
- `max_retry_limit`: Number of retry attempts

## 📁 Project Structure
