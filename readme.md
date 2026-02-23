# 🌦️ Weather + CLI Coding Agent (Chain-of-Thought Tool-Calling AI)

## 📌 Project Overview

This project is a **Command-Line AI Agent** that:

-   Uses a Large Language Model (Gemini via OpenAI SDK)
-   Implements Chain-of-Thought reasoning (START → PLAN → TOOL → OUTPUT)
-   Supports tool calling
-   Fetches real-time weather data
-   Can execute Linux commands via tool integration

It demonstrates how to build an **AI Agent with structured reasoning and
tool usage**.

------------------------------------------------------------------------

# 🎯 Problem Statement

Modern AI models can generate text, but real-world applications require:

-   Structured reasoning
-   Multi-step planning
-   Tool integration (APIs, system commands, etc.)
-   Controlled execution flow
-   Deterministic JSON outputs

Most simple chatbot implementations: - Do not separate reasoning steps -
Do not safely integrate tools - Do not control output format - Cannot
orchestrate multi-step workflows

This project solves that problem by building a:

> 🧠 Structured AI Agent that follows START → PLAN → TOOL → OUTPUT
> execution steps.

------------------------------------------------------------------------

# 💡 Why This Project Is Useful

## ✅ 1. Demonstrates Agent Architecture

Shows how modern AI agents: - Plan steps - Decide when to call tools -
Observe tool output - Generate final responses

## ✅ 2. Tool Integration Example

Includes: - Weather API tool - System command execution tool

## ✅ 3. Structured JSON Output

Forces the model to respond in a strict JSON schema using Pydantic.

## ✅ 4. Real-World Agent Foundation

This structure can be extended to: - Coding assistants - DevOps agents -
Research agents - RAG systems - Enterprise copilots

------------------------------------------------------------------------

# 🏗️ Architecture Overview

User Input\
↓\
LLM (Gemini)\
↓\
PLAN step\
↓\
If needed → TOOL call\
↓\
OBSERVE tool output\
↓\
Continue PLAN\
↓\
OUTPUT final answer

------------------------------------------------------------------------

# 📁 Project Structure

    WEATHER-CLICODING-AGENT/
    │
    ├── agent.py          # Chain-of-Thought agent with tool calling
    ├── main.py           # Simple LLM CLI interaction
    ├── requirements.txt
    ├── README.md
    └── .gitignore

------------------------------------------------------------------------

# ⚙️ Technologies Used

-   Python 3.10+
-   OpenAI SDK (Gemini API)
-   Pydantic
-   Requests
-   Dotenv
-   JSON Schema enforcement

------------------------------------------------------------------------

# 🛠️ Available Tools

### 🌦️ get_weather(city: str)

-   Fetches real-time weather information
-   Uses Open-Meteo or wttr.in API

### 🖥️ run_command(cmd: str)

-   Executes Linux commands
-   Returns system output

⚠️ Note: In production systems, command execution must be sandboxed for
security.

------------------------------------------------------------------------

# 🚀 Setup Instructions

## 1️⃣ Clone Repository

    git clone https://github.com/your-username/weather-clicoding-agent.git
    cd weather-clicoding-agent

## 2️⃣ Create Virtual Environment

    python -m venv venv
    source venv/bin/activate  # Mac/Linux
    venv\Scripts\activate   # Windows

## 3️⃣ Install Dependencies

    pip install -r requirements.txt

## 4️⃣ Create .env File

    OPENAI_API_KEY=your_api_key_here

------------------------------------------------------------------------

# ▶️ Run the Agent

### Run Chain-of-Thought Agent:

    python agent.py

### Run Simple CLI Chat:

    python main.py

------------------------------------------------------------------------

# 🧠 How It Works Internally

The system enforces a strict JSON schema:

    {
      "step": "START | PLAN | TOOL | OUTPUT",
      "content": "string",
      "tool": "string",
      "input": "string"
    }

This ensures: - Predictable execution - Structured reasoning -
Controlled tool usage

------------------------------------------------------------------------

# 🔐 Security Considerations

-   Never expose API keys in source code
-   Avoid unrestricted command execution in production
-   Always validate tool inputs
-   Use environment variables for secrets

------------------------------------------------------------------------

# 🚀 When To Use This Architecture

Use this approach when building:

-   AI coding assistants
-   AI DevOps agents
-   Automated research agents
-   Enterprise workflow agents
-   RAG-based systems
-   Task automation systems

------------------------------------------------------------------------

# 📈 Resume Value

This project demonstrates:

-   AI Agent design
-   Tool orchestration
-   API integration
-   Structured prompting
-   JSON schema enforcement
-   Multi-step reasoning systems

------------------------------------------------------------------------
