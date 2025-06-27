# FR : Image Node.js légère (20-slim)
# EN : Lightweight Node.js base image (20-slim)
FROM node:20-slim

# FR : Installe la CLI Claude globalement
# EN : Install the Claude CLI globally
RUN npm install -g @anthropic-ai/claude-code

# FR : Répertoire de travail partagé avec ton NAS / Volume 2
# EN : Shared working directory with your NAS / Volume 2
WORKDIR /workspace

# FR : Exécute “claude” par défaut
# EN : Run “claude” by default
ENTRYPOINT ["claude"]
