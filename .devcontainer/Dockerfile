FROM mcr.microsoft.com/devcontainers/python:1-3.11-bullseye

# Fix Debian Bullseye archive / security repository 404 errors
RUN echo "deb http://archive.debian.org/debian bullseye main" > /etc/apt/sources.list \
    && echo "deb http://archive.debian.org/debian-security bullseye-security main" >> /etc/apt/sources.list \
    && rm -f /etc/apt/sources.list.d/yarn.list \
    && apt-get -o Acquire::Check-Valid-Until=false update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y --no-install-recommends \
    ffmpeg \
    curl \
    git \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

# Install yt-dlp globally for media downloading tasks
RUN pip install --no-cache-dir yt-dlp
