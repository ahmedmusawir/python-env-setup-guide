# 🛠️ Python Project Environment Setup Guide

## 1. Install `pyenv`

Ensure `pyenv` is installed to manage Python versions:

```bash
curl https://pyenv.run | bash
```

After installation, add the following to your shell configuration file (`~/.bashrc`, `~/.zshrc`, etc.):

```bash
export PATH="$HOME/.pyenv/bin:$PATH"
eval "$(pyenv init --path)"
eval "$(pyenv virtualenv-init -)"
```

Reload your shell:

```bash
source ~/.bashrc  # or source ~/.zshrc
```

---

## 2. Create Project Directory

```bash
mkdir crawl4ai-exp-project-v1
cd crawl4ai-exp-project-v1
```

---

## 3. Install Target Python Version

```bash
pyenv install 3.12.3
```

---

## 4. Set Local Python Version

```bash
pyenv local 3.12.3
```

---

## 5. Install Poetry (Simplified)

Use `pip` to install Poetry directly:

```bash
pip install poetry
```

---

## 6. Initialize Poetry in the Project

```bash
poetry init
```

Follow the prompts to set up your `pyproject.toml`. For a minimal setup, you can skip adding dependencies during initialization.

---

## 7. Configure `pyproject.toml`

Replace the contents of `pyproject.toml` with the following:

```toml
[tool.poetry]
name = "crawl4ai-exp-project-v1"
version = "0.1.0"
description = "Crawl4AI-based web crawler for RAG pipelines"
authors = ["Tony Stark"]

[tool.poetry.dependencies]
python = ">=3.12,<4.0"
python-dotenv = "*"

[tool.poetry.group.dev.dependencies]
pytest = "*"

[build-system]
requires = ["poetry-core>=1.0.0"]
build-backend = "poetry.core.masonry.api"
```

**Note:** To use Poetry solely for dependency management without packaging, set `package-mode = false`:

```toml
[tool.poetry]
package-mode = false
```

---

## 8. Install Dependencies Without Installing the Root Project

```bash
poetry install --no-root
```

This installs all dependencies specified in `pyproject.toml` without installing the project itself. Useful for projects that are not intended to be packages.

---

## 9. Activate the Virtual Environment

```bash
poetry shell
```

---

## 10. (Optional) Customize the Virtual Environment Prompt

If the default environment prompt is too long (e.g., `(crawl4ai-exp-project-v1-py3.12)`), you can shorten it:

```bash
poetry config virtualenvs.prompt "c4ai"
```

Then recreate the virtual environment:

```bash
poetry env remove python
poetry install --no-root
poetry shell
```

Your prompt will now display as `(c4ai)` instead.

---

## 11. Test the Setup

Create a simple `main.py` to verify the environment:

```python
print("Environment setup is successful!")
```

Run the script:

```bash
python main.py
```

You should see:

```
Environment setup is successful!
```

---

This is the official Stark-Certified Python rig for repeatable, clean, and professional project environments.
