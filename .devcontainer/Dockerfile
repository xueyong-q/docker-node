FROM node:14

ENV LANG C.UTF-8
ARG USERNAME=node
COPY ohmyzsh.sh /tmp/

RUN apt-get update \
    && apt-get -y install --no-install-recommends apt-utils dialog 2>&1 \
    #
    # Verify git, needed tools installed
    && apt-get -y install git openssh-client less iproute2 procps curl lsb-release vim zsh jq \
    #
    # add permissions
    && chmod +x /tmp/ohmyzsh.sh \
    #
    # 设置环境变量
    && echo "export PATH=/home/${USERNAME}/.yarn/bin:\$PATH" >> /home/${USERNAME}/.envrc \
    && sudo -u ${USERNAME} touch /home/${USERNAME}/.zshrc \
    && echo ". ~/.envrc" > /home/${USERNAME}/.zshrc \
    #
    # Clean up
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*