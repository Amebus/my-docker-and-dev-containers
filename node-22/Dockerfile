# Docker has specific installation instructions for each operating system.
# Please refer to the official documentation at https://docker.com/get-started/

# Pull the Node.js Docker image:
# docker pull node:22-alpine

# # Create a Node.js container and start a Shell session:
# docker run -it --rm --entrypoint sh node:22-alpine

# # Verify the Node.js version:
# node -v # Should print "v22.13.0".

# # Download and install pnpm:
# corepack enable pnpm

# # Verify pnpm version:
# pnpm -v

FROM node:22-alpine


RUN node -v 
# Should print "v22.13.0".


# Installa strumenti di sviluppo (opzionale)

# RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
#     DEBIAN_FRONTEND=noninteractive apt-get install -y \
#     git \
#     vim \
#     curl && \
#     apt-get clean && rm -rf /var/lib/apt/lists/*
RUN apk add --no-cache \
    git \
    bash \
    curl
RUN npm install -g pnpm \
    npm install -g npm-check-updates

# Crea una directory di lavoro
WORKDIR /workspace

# Copia i file di progetto (opzionale)
# COPY . /workspace

# Installa dipendenze globali (opzionale)

# Imposta l'utente non root

ARG USERNAME=vscode
RUN adduser --disabled-password --gecos "" $USERNAME
USER $USERNAME
# ARG USERNAME=vscode
# RUN useradd -m $USERNAME
# USER $USERNAME

# Porta di default per Node.js
EXPOSE 3000

CMD ["pnpm"]