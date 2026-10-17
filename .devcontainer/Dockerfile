FROM mcr.microsoft.com/devcontainers/python:1-3.11-bullseye

# Install system dependencies commonly needed for YouTube media tools
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y --no-install-recommends \
    ffmpeg \
    curl \
    git \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Install yt-dlp globally for media downloading tasks
RUN pip install --no-cache-dir yt-dlp
