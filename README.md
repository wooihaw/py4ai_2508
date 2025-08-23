# py4ai_2508
Examples for Python for AI

## Setup Guide

Follow the steps below to install the required tools, restore the Python environment, and launch Jupyter Lab.

### 1) Install `uv` and Git (Windows)

Use PowerShell (run as a regular user):

```powershell
# Install uv
irm https://astral.sh/uv/install.ps1 | iex

# Verify installation
uv --version

# Install Git (using winget)
winget install --id Git.Git -e --source winget

# Verify Git
git --version
```

Notes:
- If `uv` is not found after install, close and reopen PowerShell.
- If `winget` is unavailable, download Git for Windows from https://git-scm.com/download/win.

### 2) Install `uv` and Git (Linux)

Run the appropriate commands for your distribution:

```bash
# Install uv
curl -fsSL https://astral.sh/uv/install.sh | sh

# Ensure uv is on your PATH (restart shell if needed)
# Common install path: ~/.local/bin
uv --version

# Install Git
# Debian/Ubuntu
sudo apt update && sudo apt install -y git
# Fedora
# sudo dnf install -y git
# Arch
# sudo pacman -S --noconfirm git

git --version
```

Notes:
- If `uv` is not found, ensure `~/.local/bin` is on your `PATH` or restart your terminal session.

### 3) Restore the environment

From the project root (where `pyproject.toml` is located), run:

```bash
uv sync
```

This will create/refresh a virtual environment and install all dependencies pinned in `uv.lock`.

### 4) Launch Jupyter Lab

Start Jupyter Lab inside the managed environment:

```bash
uv run jupyter-lab
```

Tip: The first run may download a matching Python runtime; subsequent runs will be faster.
