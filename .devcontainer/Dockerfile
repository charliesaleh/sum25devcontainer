FROM mcr.microsoft.com/devcontainers/base:ubuntu

# install packages needed
RUN apt-get update && apt-get install -y \
    curl ca-certificates gnupg \
    git build-essential python3 python3-pip pkg-config \
    linux-libc-dev \
  && rm -rf /var/lib/apt/lists/*

# Install Node LTS from NodeSource (prebuilt, avoids compiling OpenSSL)
RUN curl -fsSL https://deb.nodesource.com/setup_lts.x | bash - \
  && apt-get install -y nodejs \
  && rm -rf /var/lib/apt/lists/*

# Optional sanity check during build (helps surface failures in the creation log)
RUN node -v && npm -v && g++ --version

USER vscode
