FROM node:22.22.3-bookworm-slim

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
        ca-certificates \
        git \
        git-flow \
        openssh-client && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /workspaces/nest-boilerplate

ENV NPM_CONFIG_PREFIX=/home/node/.npm-global
ENV PATH=$PATH:/home/node/.npm-global/bin

RUN mkdir -p /home/node/.vscode-server/data/User/History \
             /workspaces/app/node_modules && \
    chown -R node:node /home/node /workspaces/app

USER node