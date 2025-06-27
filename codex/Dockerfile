# FR : Base Node.js 20-slim pour minimiser la taille
# EN : Node.js 20-slim base to minimise size
FROM node:20-slim

# FR : Installation de la CLI Codex (OpenAI)
# EN : Install the Codex CLI (OpenAI)
RUN npm install -g @openai/codex

# FR : Point de montage des fichiers de travail
# EN : Working directory mount point
WORKDIR /workspace

# FR : Exécute “codex” quand le conteneur démarre
# EN : Run “codex” when the container starts
ENTRYPOINT ["codex"]
