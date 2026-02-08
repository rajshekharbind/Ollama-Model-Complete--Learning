# Ollama – Complete  Learning 

A hands-on, structured guide to **Ollama** covering local LLM usage, LangChain integration, REST APIs, tool calling, Ollama Cloud, and advanced experiments with models like **Gemma 3 (4B)**, including vision and multimodal workflows.

---

## 📌 What is Ollama?

Ollama is a platform that allows you to **run, manage, and experiment with large language models (LLMs) locally** and in the cloud. It provides a simple CLI, REST API, and library support to work with modern open-source models like LLaMA, Gemma, Qwen, Mistral, and more.

**Key idea:** *Local-first AI with optional cloud scalability.*

---

## 🧠 Why Use Ollama?

* 🚀 Run LLMs locally (privacy + speed)
* 🔒 No data leaves your machine (local mode)
* 🧩 Easy integration with Python, LangChain, REST APIs
* 🛠️ Built-in support for tool calling & function execution
* ☁️ Ollama Cloud for scalable inference
* 🧪 Perfect for learning, experimentation, and R&D

---

## 📂 Project Structure

```
.
├── Ollama.ipynb                    # Core Ollama usage & CLI experiments
├── Ollama using Rest API.ipynb     # REST API calls (generate, chat, models)
├── Ollama Using LangChain.ipynb    # LangChain + Ollama integration
├── Tool Calling.ipynb              # Function / tool calling with Ollama
├── Ollama Cloud.ipynb              # Cloud-based inference concepts
├── Modelfile.txt                   # Custom model configuration
├── Ollama Short notes.docx         # Quick theory notes
├── README.md                       # This documentation
```

---

## ⚙️ Ollama Core Concepts

## 🧾 Common Ollama Commands

### 🔹 Ollama CLI Commands

```bash
# Check Ollama version
ollama --version

# List available models
ollama list

# Pull a model
ollama pull gemma3:4b

# Run a model interactively
ollama run gemma3:4b

# Run with a prompt
ollama run gemma3:4b "Explain LLMs in simple words"

# Remove a model
ollama rm gemma3:4b
```

---

### 🔹 Ollama REST API (curl examples)

```bash
# Generate text
curl http://localhost:11434/api/generate \
  -d '{"model": "gemma3:4b", "prompt": "What is GenAI?"}'

# Chat API
curl http://localhost:11434/api/chat \
  -d '{"model": "gemma3:4b", "messages": [{"role": "user", "content": "Hello"}]}'

# List models via API
curl http://localhost:11434/api/tags
```

---

### 🔹 Python (Ollama Library)

```python
from ollama import chat

response = chat(
    model="gemma3:4b",
    messages=[{"role": "user", "content": "Explain tool calling"}]
)
print(response["message"]["content"])
```

---

### 🔹 LangChain + Ollama

```python
from langchain_community.llms import Ollama

llm = Ollama(model="gemma3:4b")
print(llm.invoke("What is RAG?"))
```

---

### 🔹 Tool Calling (Conceptual Command)

* Define tools (functions)
* Pass tool schema to model
* Model decides when to call tools

Used for:

* Calculations
* API calls
* Database queries

---

### 🔹 Ollama Cloud (Conceptual Commands)

```text
Prompt → Cloud Endpoint → GPU Inference → Response
```

Used when:

* Large models (30B+)
* High traffic apps
* Production workloads

---

### 1️⃣ Ollama CLI & Library

* Pull models (`ollama pull gemma3:4b`)
* Run models locally (`ollama run gemma3:4b`)
* Manage models (list, delete, update)
* Python library for programmatic access

**Benefit:** Simple developer experience with production-ready models.

---

### 2️⃣ Ollama REST API

Ollama exposes a local REST server:

* `/api/generate`
* `/api/chat`
* `/api/tags` (list models)

**Use cases:**

* Backend integration
* Web apps
* Microservices

**Benefits:**

* Language agnostic
* Easy to scale
* Works with Docker & cloud infra

---

### 3️⃣ Ollama with LangChain

LangChain enables:

* Prompt templates
* Chains & agents
* Memory
* Tool usage

**Workflow:**

```
User → LangChain → Ollama Model → Response
```

**Benefits:**

* Build RAG pipelines
* AI agents
* Conversational memory

---

## 🛠️ Tool Calling with Ollama

Tool calling allows models to:

* Call Python functions
* Execute APIs
* Perform structured reasoning

**Examples:**

* Calculator tools
* Database queries
* File operations
* External API calls

**Why it matters:**

> Turns LLMs into **AI agents**, not just chatbots.

---

## ☁️ Ollama Cloud – How Large Models Work in Cloud

### How Cloud LLMs Work

1. User sends prompt
2. Request hits cloud inference server
3. Model runs on GPU/TPU
4. Response streamed back

### Benefits of Cloud Models

* ⚡ High performance GPUs
* 📈 Auto scaling
* 🧠 Large models (70B+)
* 🔄 No local hardware dependency

### Local vs Cloud

| Feature | Local Ollama          | Ollama Cloud           |
| ------- | --------------------- | ---------------------- |
| Privacy | ✅ High                | ⚠️ Medium              |
| Cost    | ✅ Low                 | 💰 Usage based         |
| Speed   | ⚡ Fast (small models) | 🚀 Fast (large models) |
| Offline | ✅ Yes                 | ❌ No                   |

---

## 🧪 Model Experiments – Gemma 3 (4B)

### Why Gemma 3 (4B)?

* Lightweight
* Fast inference
* High-quality reasoning
* Ideal for laptops

### Experiments Covered

* Text generation
* Instruction following
* Tool calling compatibility
* Vision & multimodal prompts (image → text)

---

## 🖼️ Vision & Image → Text (Multimodal)

Supported workflows:

* Image captioning
* OCR-like text extraction
* Visual reasoning

**Use cases:**

* Document processing
* Image understanding
* AI assistants with vision

---

## 🤖 Model Capability Matrix

| Feature       | Gemma 3 | LLaMA | Qwen | Mistral |
| ------------- | ------- | ----- | ---- | ------- |
| Tool Calling  | ✅       | ✅     | ✅    | ⚠️      |
| Vision        | ✅       | ❌     | ⚠️   | ❌       |
| Cloud Support | ✅       | ✅     | ✅    | ✅       |
| RAG Friendly  | ✅       | ✅     | ✅    | ✅       |

---

## 📚 Learning Path (Recommended)

### Beginner

1. Ollama CLI basics
2. Pull & run models
3. Simple text generation

### Intermediate

4. REST API usage
5. LangChain integration
6. Prompt engineering

### Advanced

7. Tool calling
8. Vision models
9. RAG pipelines
10. Cloud deployment

---

## 🎯 Benefits of This Setup

* Learn LLMs practically
* Build production-ready AI apps
* No vendor lock-in
* Works locally & in cloud
* Ideal for students & professionals

---

## 🚀 Future Extensions

* RAG with vector databases
* Multi-agent systems
* Fine-tuning custom models
* Production deployment (Docker, Kubernetes)

---



Happy Building 🚀

