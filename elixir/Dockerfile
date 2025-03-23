FROM elixir:1.18.3-alpine

RUN apk add --no-cache \
    git \
    bash \
    curl

# Installa Hex e Rebar (necessari per Elixir)
RUN mix local.hex --force && mix local.rebar --force

# Imposta la cartella di lavoro
WORKDIR /workspace

ARG USERNAME=vscode
RUN adduser --disabled-password --gecos "" $USERNAME
USER $USERNAME

# Porta di default per Node.js
EXPOSE 3000

CMD ["mix"]
