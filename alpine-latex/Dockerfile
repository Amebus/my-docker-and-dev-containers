# Usa Alpine come base
FROM alpine:latest

# Ambiente non interattivo per le installazioni
ENV DEBIAN_FRONTEND=noninteractive

# Installazione di dipendenze base, TeX Live e font comuni
RUN apk add --no-cache \
    bash \
    curl \
    perl \
    fontconfig \
    ghostscript \
    ttf-dejavu \
    ttf-droid \
    ttf-freefont \
    ttf-liberation \
    ttf-linux-libertine \
    texmf-dist \
    && apk add --no-cache texlive-full \
    && rm -rf /var/cache/apk/*

ARG USERNAME=vscode
RUN adduser --disabled-password --gecos "" $USERNAME
USER $USERNAME

# Imposta la directory di lavoro
WORKDIR /workspace