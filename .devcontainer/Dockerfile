ARG VERSION
FROM node:${VERSION}

ARG USERNAME
ARG LANG
ENV LANG=${LANG}
COPY ohmyzsh.sh /usr/bin/

RUN apt-get update \
    && apt-get -y install --no-install-recommends apt-utils dialog 2>&1 \
    #
    # Verify git, needed tools installed
    && apt-get -y install sudo git openssh-client less iproute2 procps curl lsb-release vim zsh jq \
    && echo "${USERNAME} ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/${USERNAME} \
    && chmod 0440 /etc/sudoers.d/${USERNAME} \
    #
    # add permissions
    && chmod +x /usr/bin/ohmyzsh.sh \
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