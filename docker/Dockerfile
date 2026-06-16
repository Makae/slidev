# Minimal Slidev image
FROM node:lts-alpine

WORKDIR /working-dir

RUN touch ~/.profile

ENV SHELL=/bin/sh
ENV ENV=~/.profile
ENV PATH="$PATH:/root/.local/share/pnpm/bin"

RUN npm install -g pnpm
RUN pnpm setup
RUN pnpm install -g @slidev/cli@^0.50.0 @slidev/theme-seriph@latest

COPY package.json ./
COPY pnpm-workspace.yaml ./

RUN pnpm install


EXPOSE 3030
