FROM python:3.8-slim

# Set up non-root user
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    #
    # [Optional] Add sudo support for the non-root user
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# Install essential development tools
RUN apt-get update && apt-get install -y \
    git \
    curl \
    wget \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# Set up user environment
USER $USERNAME
WORKDIR /home/$USERNAME

# Install Poetry for Python package management
RUN curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python -

# Add Poetry's bin directory to PATH
ENV PATH="/home/${USERNAME}/.poetry/bin:${PATH}"

# Copy in the project files
COPY . /home/$USERNAME/workspace

# Install project dependencies
WORKDIR /home/$USERNAME/workspace
RUN poetry install

CMD ["/bin/bash"]
