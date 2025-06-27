<!-- ────────────────────────────────────────────────────────────────────────────── -->

# Gemini • Claude • Codex – Dockerized CLI Tools

Google Gemini CLI • Anthropic Claude Code CLI • OpenAI Codex CLI

<!-- ────────────────────────────────────────────────────────────────────────────── -->

A **one-stop Docker workspace** that packages the three most popular LLM command-line interfaces:

| CLI tool            | Model family                        | Docker base    | Image tag example               |
| ------------------- | ----------------------------------- | -------------- | ------------------------------- |
| **Gemini CLI**      | Google Gemini (Generative Language) | `node:20-slim` | `diablotin74/gemini-cli:latest` |
| **Claude Code CLI** | Anthropic Claude 3                  | `node:20-slim` | `diablotin74/claude-cli:latest` |
| **Codex CLI**       | OpenAI Codex / GPT-4o               | `node:20-slim` | `diablotin74/codex-cli:latest`  |

With these images you can chat with the models, refactor code, run shell commands, or automate docs **directly from your terminal—no local Node setup needed**.

---

## ✨ Features

* **Ready-to-run**: each Dockerfile installs the latest CLI release in one layer.
* **Ultra-light**: based on `node:20-slim` (\~100 MB download, \~350 MB image).
* **Volume mount–ready**: designed to bind any host folder (e.g. your NAS) to `/workspace` so the AI can read & write your files.
* **Multi-arch roadmap**: images will soon be built for `linux/amd64` **and** `linux/arm64` via Buildx.
* **Open-source, no vendor lock-in**: inspect, fork, PR welcome!

---

## 🚀 Quick Start

```bash
# Pull the image you need
docker pull diablotin74/gemini-cli:latest

# Run it and mount your local project
docker run -it -v "$PWD":/workspace diablotin74/gemini-cli

# First-time Google OAuth flow appears in the terminal
```

For Claude or Codex just replace the image name.
→ **Pro tip**: store your API keys in environment variables or Docker secrets:

```bash
docker run -it \
  -e ANTHROPIC_API_KEY=sk-… \
  -v "$PWD":/workspace \
  diablotin74/claude-cli
```

---

## 🔧 Building from source

```bash
git clone https://github.com/DiAbL0Tin/gemini-claude-codex-cli-docker.git
cd gemini            # or claude, codex
docker build -t my-gemini-cli .
```

Edit the Dockerfile if you want to pin a specific CLI version.

---

## 📂 Using with docker-compose / Portainer

```yaml
version: "3.9"
services:
  gemini:
    image: diablotin74/gemini-cli:latest
    volumes:
      - /mnt/md1/Volume2:/workspace   # full access to your NAS Volume 2
    tty: true
    stdin_open: true
```

Duplicate the service block for `claude` and `codex` if you prefer a single stack.

---

## 🗓 Roadmap

* [ ] GitHub Actions multi-arch build (amd64 + arm64)
* [ ] Automated daily “latest” refresh
* [ ] Optional Alpine base for even smaller footprint
* [ ] Example notebooks & VS Code DevContainer

---

## 👐 Contributing

Star the repo ⭐, open issues 🐛, or submit pull requests — every idea is welcome!

---

## 📜 License

MIT © 2025 DiAbL0Tin

<!-- ────────────────────────────────────────────────────────────────────────────── -->

# 🇫🇷 Présentation : Gemini • Claude • Codex – CLIs Dockerisés

Google Gemini CLI • Anthropic Claude Code CLI • OpenAI Codex CLI

<!-- ────────────────────────────────────────────────────────────────────────────── -->

Un **espace de travail Docker tout-en-un** qui regroupe les trois interfaces ligne de commande LLM les plus populaires :

| CLI                 | Famille de modèle     | Base Docker    | Exemple de tag                  |
| ------------------- | --------------------- | -------------- | ------------------------------- |
| **Gemini CLI**      | Google Gemini         | `node:20-slim` | `diablotin74/gemini-cli:latest` |
| **Claude Code CLI** | Anthropic Claude 3    | `node:20-slim` | `diablotin74/claude-cli:latest` |
| **Codex CLI**       | OpenAI Codex / GPT-4o | `node:20-slim` | `diablotin74/codex-cli:latest`  |

**But : discuter, générer ou refactoriser ton code directement depuis le terminal**, sans installer Node ni dépendances sur ta machine.

---

## ✨ Fonctionnalités

* **Prêt à l’emploi** : chaque Dockerfile installe la dernière version de la CLI.
* **Taille réduite** : images basées sur `node:20-slim`.
* **Montage facile** d’un dossier hôte sur `/workspace` (NAS ou PC).
* **Bientôt multi-architecture** (`amd64` / `arm64`) via Buildx.
* **100 % open-source** : forke, modifie, propose des PR librement.

---

## 🚀 Démarrage rapide

```bash
docker pull diablotin74/claude-cli:latest
docker run -it -e ANTHROPIC_API_KEY=sk-... -v "D:/Projets":/workspace diablotin74/claude-cli
```

Même principe pour `gemini-cli` et `codex-cli`.

---

## 🔧 Construire l’image soi-même

```bash
git clone https://github.com/DiAbL0Tin/gemini-claude-codex-cli-docker.git
cd codex
docker build -t mon-codex-cli .
```

---

## 📂 Exemple `docker-compose.yml`

```yaml
version: "3.9"
services:
  codex:
    image: diablotin74/codex-cli:latest
    environment:
      - OPENAI_API_KEY=${OPENAI_API_KEY}
    volumes:
      - /mnt/md1/Volume2:/workspace
    tty: true
    stdin_open: true
```

---

## 🛣 Feuille de route

* [ ] Build multi-arch automatisé
* [ ] Mise à jour quotidienne du tag `latest`
* [ ] Exemple d’intégration Portainer
* [ ] Guide complet des variables d’environnement

---

## 🤝 Contribuer

Signale un bug, propose une amélioration, ou laisse une ⭐ : toute aide est appréciée !

---

## 📜 Licence

MIT © 2025 DiAbL0Tin
