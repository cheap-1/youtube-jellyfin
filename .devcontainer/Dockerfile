FROM mcr.microsoft.com/devcontainers/python:1-3.11-bullseye

# Remove stale/broken external repositories (like yarn) pre-included in the base image
RUN rm -f /etc/apt/sources.list.d/yarn.list \
    && apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y --no-install-recommends \
    ffmpeg \
    curl \
    git \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Install yt-dlp globally for media downloading tasks
RUN pip install --no-cache-dir yt-dlp
