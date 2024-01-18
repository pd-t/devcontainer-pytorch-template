FROM thomasfraunholz/docker-cuda-poetry:1.6.1-117
ARG USER_NAME=user
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Create the user
RUN groupadd --gid $USER_GID $USER_NAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USER_NAME \
    #
    # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USER_NAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USER_NAME \
    && chmod 0440 /etc/sudoers.d/$USER_NAME

# ********************************************************
# * Anything else you want to do like clean up goes here *
# ********************************************************
RUN apt-get update && apt-get install -y \
    git \
    curl \
    wget \
    vim \
    nano \
    htop \
    tmux \
    zsh \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*
RUN ln -s /usr/bin/python3 /usr/bin/python
ENV PATH="$PATH:/home/user/.local/bin"
SHELL ["/bin/bash", "-c"]
# [Optional] Set the default user. Omit if you want to keep the default as root.
USER $USER_NAME
