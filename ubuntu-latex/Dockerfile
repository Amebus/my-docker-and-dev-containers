# Usa un'immagine base con un editor di testo e LaTeX
FROM ubuntu:20.04

# Installazione di pacchetti essenziali
RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    texlive-full \
    latexmk \
    ghostscript \
    curl \
    git && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Configurazione utente
ARG USERNAME=vscode
RUN useradd -m -s /bin/bash $USERNAME
USER $USERNAME

WORKDIR /workspaces