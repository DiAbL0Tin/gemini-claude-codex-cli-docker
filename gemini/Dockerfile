# FR : Utilise une image Node.js légère pour garder l’image petite
# EN : Use a slim Node.js image to keep the final image small
FROM node:20-slim

# FR : Permet d’injecter la clé à la build (facultatif)
# EN : Allow optional key injection at build-time
ARG GEMINI_API_KEY

# FR : Installe la CLI Gemini globalement
# EN : Install the Gemini CLI globally
RUN npm install -g @google/gemini-cli

# FR : Expose la clé à l’exécution si elle a été fournie
# EN : Expose the key at runtime if provided
ENV GEMINI_API_KEY=${GEMINI_API_KEY}

# FR : Dossier de travail de l’utilisateur
# EN : User working directory
WORKDIR /workspace

# FR : Lance “gemini” par défaut
# EN : Start “gemini” by default
ENTRYPOINT ["gemini"]