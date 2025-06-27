# FR : Utilise une image Node.js légère pour garder l’image petite
# EN : Use a slim Node.js image to keep the final image small
FROM node:20-slim

# FR : Installe la CLI Gemini en global
# EN : Install the Gemini CLI globally
RUN npm install -g @google/gemini-cli

# FR : Définit le dossier de travail où tes fichiers seront disponibles
# EN : Set the working directory where your files will be mounted
WORKDIR /workspace

# FR : Lance “gemini” par défaut quand le conteneur démarre
# EN : Start “gemini” by default when the container runs
ENTRYPOINT ["gemini"]
