FROM mcr.microsoft.com/vscode/devcontainers/base:ubuntu-22.04

ARG TFSWITCH_VERSION=1.2.4
ARG TFLINT_VERSION=v0.55.0

ARG USERNAME=vscode

USER ${USERNAME}

# install and configure zsh
RUN sudo apt-get install -y zsh
ENV SHELL /bin/zsh
RUN wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh || true

# install tfswitch
ENV PATH=$PATH:/home/${USERNAME}/bin
RUN curl -L https://raw.githubusercontent.com/warrensbox/terraform-switcher/master/install.sh | bash -s -- -b /home/${USERNAME}/bin $TFSWITCH_VERSION

# install tflint
RUN curl -s https://raw.githubusercontent.com/terraform-linters/tflint/${TFLINT_VERSION}/install_linux.sh | bash
