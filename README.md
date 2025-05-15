# 🐍 Python Environment Setup Guide (Repeatable for All Projects)

This is Tony Stark's official Python environment rig — designed to be reused across all serious AI, automation, scraping, and LangChain projects. This is also future-proofed for Udemy tutorial inclusion.

---

## ✅ Step-by-Step Setup (Repeatable Rig)

### 1. Install `pyenv`

```bash
curl https://pyenv.run | bash
```

> Also add `pyenv init` to your shell profile (`.bashrc`, `.zshrc`, etc.)

---

### 2. Create Project Folder and Enter It

```bash
mkdir crawl4ai-exp-project-v1
cd crawl4ai-exp-project-v1
```

---

### 3. Install Target Python Version (e.g., 3.12.3)

```bash
pyenv install 3.12.3
```

---

### 4. Activate It for the Project

```bash
pyenv local 3.12.3
```

> This creates a `.python-version` file in the current directory.

---

### 5. Install Poetry (If Not Already Installed)

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

---

### 6. Initialize Poetry in the Folder

```bash
poetry init --no-interaction
```

---

### 7. Replace `pyproject.toml` With the Custom Rig

```toml
[tool.poetry]
name = "crawl4ai-exp-project-v1"
version = "0.1.0"
description = "Crawl4AI-based web crawler for RAG pipelines"
authors = ["Tony Stark"]

[tool.poetry.dependencies]
python = ">=3.12,<4.0"
crawl4ai = "*"
playwright = "*"
python-dotenv = "*"

[tool.poetry.group.dev.dependencies]
pytest = "*"

[build-system]
requires = ["poetry-core>=1.0.0"]
build-backend = "poetry.core.masonry.api"

# 📦 Uncomment when project structure grows:
# packages = [
#   { include = "agents" },
#   { include = "utils" },
#   { include = "langgraph" }
# ]
```

> 🔍 **Note:** TOML doesn't officially support `#` comments inside arrays. You must move that block outside or comment the entire array manually as a string if needed.

---

### 8. Install Dependencies Without Project Root Packaging

```bash
poetry install --no-root
```

---

### 9. Enable `poetry shell` (Poetry v2+ doesn’t include it by default)

```bash
poetry self add poetry-plugin-shell
```

Then:

```bash
poetry shell
```

> 💬 Inside the shell, your prompt will look like:
> `(crawl4ai-exp-project-v1-py3.12)` — You can change this name (see bottom of this doc)

---

### 10. Test With a Simple Run

```bash
python main.py
```

✅ Everything should execute inside the poetry-managed virtual environment.

---

## 🎨 How to Shorten the Virtualenv Name in Terminal Prompt

Poetry names the virtualenv based on project name + Python version. To customize it:

1. Rename the folder under:

```bash
~/.cache/pypoetry/virtualenvs/
```

2. Update the `.venv` symlink in your project (optional)
3. Or just ignore it — it’s only cosmetic 😅

---

## 🧪 Verified by Tony & Jarvis

This is the official rig that powers:

* CyberGenesis
* CyberDocs
* CyberVector
* And all LangGraph AI agent orchestration labs

Clone. Repeat. Dominate. 💥

