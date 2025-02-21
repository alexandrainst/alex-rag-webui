FROM mcr.microsoft.com/vscode/devcontainers/python:3.11-bookworm

ENV PYTHONUNBUFFERED 1

COPY backend/requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmp

RUN apt update && export DEBIAN_FRONTEND=noninteractive \
    && apt -y install --no-install-recommends ffmpeg sqlite3 \
    && rm -rf /var/lib/apt/lists/*

RUN curl -fsSL https://ollama.com/install.sh | sh

# TODO: Add ollama serve as default cmd (done from docker compose presently)