
FROM python:3.11-slim

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    git \
    curl \
    vim \
    && rm -rf /var/lib/apt/lists/*

# Set up a non-root user (optional, but recommended for devcontainers)
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME

# Set work directory
WORKDIR /workspace

# Install pipx and common Python dev tools
RUN pip install --no-cache-dir pipx \
    && pipx ensurepath \
    && pipx install pipenv

# Switch to non-root user
USER $USERNAME

# Default command
CMD [ "bash" ]