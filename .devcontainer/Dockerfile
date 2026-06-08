FROM mcr.microsoft.com/devcontainers/jekyll

USER root

RUN set -eux; \
    mkdir -p /usr/share/keyrings; \
    curl -fsSL https://dl.yarnpkg.com/debian/pubkey.gpg | gpg --batch --yes --dearmor -o /usr/share/keyrings/yarn-archive-keyring.gpg; \
    echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/yarn-archive-keyring.gpg] https://dl.yarnpkg.com/debian/ stable main" > /etc/apt/sources.list.d/yarn.list; \
    apt-get update; \
    apt-get install -y --no-install-recommends \
        build-essential \
        imagemagick \
        inotify-tools \
        jupyter-nbconvert \
        procps \
        ruby-full \
        zlib1g-dev; \
    apt-get clean; \
    rm -rf /var/lib/apt/lists/*
