FROM mcr.microsoft.com/devcontainers/universal:2-linux
# Install the xz-utils package
RUN apt-get update

RUN apt-get update && apt-get install -y \
    curl \
    gnupg \
    xz-utils \
    ca-certificates \
    software-properties-common

# installing node.js
RUN curl -fsSL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs && \
    npm install -g npm@latest

# installing Go
ENV GO_VERSION=1.22.2
RUN curl -LO https://golang.org/dl/go${GO_VERSION}.linux-amd64.tar.gz && \
    rm -rf /usr/local/go && \
    tar -C /usr/local -xzf go${GO_VERSION}.linux-amd64.tar.gz && \
    rm go${GO_VERSION}.linux-amd64.tar.gz

# adding Go to path
ENV PATH=$PATH:/usr/local/go/bin